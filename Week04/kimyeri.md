# Network Layer

- Router을 통해 이동한다. 이 장치가 목적지를 분석하여 보낸다.
- Router에서 Process delay가 발생한다.
- 목적지까지 패킷을 어떻게 잘 보낼 것인지에 대한 Layer이다.

## 기능

1. Forwarding : router 외부로 내보내기
2. Routing : 목적지까지 가기 위해 경로를 결정하는 부분

⇒ 목적지 확인 후 Forwarding Table에서 찾아 알맞은 곳으로 내보내야 한다.

- Forwarding Table
  - 어떤 interface로 나아가야할지 표로 정리돼있음
  - 주소 범위로 관리된다.
  - Longest Prefix Matching으로 가장 길게 matching, 가장 구체적인 곳을 선택하여 보낸다.

## IP datagram (Packet)

### Header

- source IP, dest IP ⇒ 가장 중요한 필드
- time to live : 한정 시간 만큼만 패킷이 유효함. 영원하다면 네트워크 리소스가 낭비된다.
- upper layer: TCP or UDP, 수신자를 위해 있다.

⇒ Overhead : 20 TCP + 20 IP + app layer overhead (헤더 사이즈)

### IP Address - IPv4

- 32bit
- 네트워크 interface를 지칭함
  - router는 인터페이스가 많으므로 IP주소가 여러개이다.
- 8bits씩 끝어 10진수로 읽는다.

### Hierarchical Addressing : IP Prefixes

- Scalability Challange : 호스트 별로 다 달라 forwarding table의 entry 수가 너무 많아질 것임
- 12.34.158.0/24 ⇒ 24-bit prefix : 네트워크 bit를 명시하고 2^8만큼의 주소를 갖을 수 있음
  → Subnet Mask 를 이용한다. ex. 255.255.255.0
- prefix가 동일하면 같은 네트워크이다. ⇒ forwarding table이 단순해진다.

### Addressing의 종류

1. 과거 - Classful

   A : / 8 blocks → 2^24 hosts ⇒ 하지만 기관은 128개로 너무 작음

   B : / 16 blocks → 2^16 hosts

   C : /24 blocks → 2^8 hosts

   ⇒ 호스트와 기관 개수가 비효율적이고, 유연하지 않은 방법이다.

2. 최근 - **Classless Inter-Domain Routing (CIDR)**

   Prefix 단위가 자유로운 것

   1000의 host가 필요하다고 할 때,

   과거 : /24 짜리 4개를 받아야함

   CIDR : /22로 총 1024개의 hosts가 가능

   ⇒ 네트워크 크기에 맞춰서 자유롭게 이용한다. /nn으로 명시하면 됨

### Longest Prefix Match Forwarding

Forwarding Table에서 가장 Prefix가 긴 것을 고르면 된다.

⇒ matching 되는 것 중 구체적으로 맞는 것을 고르는 방법

### Subnets

같은 Prefix를 가진 Device의 집합

라우터를 거치지 않고 접근이 가능한 host 집합이다.

router는 여러 인터페이스가 있고, 이를 통해 서브넷이 연결돼있다. 즉, router가 교집합인 셈..

### 부족 현상 - IPv6

32bits 인 IPv4는 40억 정도가 지원이 가능한데 산업화 이후로 부족해지기 시작하였다.

그래서 96년도에 128bits 주소 공간을 사용하기로 했지만, NAT로 IPv4를 유지하고 있다.

### NAT

Network Address Translation. 근본적인 원인을 해결한 것이 아닌 방법

Gateway 전에서서는 Local Address를 이용하다가 지나면서 Gateway의 IP를 할당 받음

내부에서는 unique 해보이지만, 외부에서는 아니기에 변환이 필요하다.

이때, IP와 Port # 두개를 바꾼다.

⇒ 문제

1. 디자인 상의 문제 - Layer가 무너진다.

   Transport Layer의 소관인 segment의 port #을 바꾼다.

   절대로 깨끗한 방법이 아니다.

2. ..

### DHCP

Dynamic Host Configuration Protocol → 어디서든 IP를 동적으로 할당하는데 이 방법

고정 IP면 모두에게 할당해야함 → 너무 비효율

⇒ 유연하게 적용하여 그때 그때 IP를 할당한다. 필요할 때 주고, 아니라면 회수한다.

- 인터넷에 연결되기 위해 필요한 정보들
  - IP | 192.168.1.47
  - Maks | 255.255.255.0
  - Router | 192.168.1.1
  - DNS | 192.168.1.1
    → Router와 DNS 둘다 router에서 동작 중이다.

**#️⃣  Scenario**

1. C → DHCP Server : DHCP discover
   1. src : 0.0.0.0./ 68 : 아직 할당된 게 없다고
   2. broadcast를 하는 방법 ⇒ **dest : 255.255.255.255/67**

      이러면 67번을 열어둔 DHCP 서버만 응답한다.

   3. transaction ID : 654
2. S → C : DHCP offer
   1. **src : 할당 해줌**
   2. **dest : 255.255.255.255/68**

      broadcast하여 68만 열려있는 Client만 의미있게 받아드린다.

   3. transaction ID : 654
3. C → S : DHCP Request
   1. offer을 수락한다는 의미
   2. src: 0.0.0.0/68 ⇒ 아직 확정 아님
   3. dest :255.255.255.255/67
   4. **transaction ID : 이전 꺼 + 1** 즉, 655를 보낸다. OK의 의미
4. S → C : DHCP ACK
   1. req에 대한 확인차, 이 이후로 필요한 4가지 정보들이 들어온다.
   2. src : 223.1.2.5/67
   3. dest : 255.255.255.255/68
   4. transaction ID : 655

⇒ 왜 여러 단계?

offer는 여러 DHCP로 부터 올 수 있다. 하나를 골라서 req을 하게 도는 것이다.

⇒ DHCP Server는 Router에 있다.

### IP Fragmentation

Header에는 16-bit identifier | flags | fragment offset 필드가 있다.

이는 Packet이 Fragment될 때 사용하게 되는데 link마다 mtu가 달라 발생한다.

- length : 잘라진 길이 (1500이라면 실 데이터는 1480, 20은 헤더 사이즈)
- ID : Packet ID (같은 Packet은 동일하다.)
- fragFlag : 1 (내 뒤에 파편이 있음을 의미) / 0 (더이상 없음)
- offset : 기존 data에서 시작할 부분을 기록해둔다. (두번째 파편은 185) ⇒ 순서임

→ 이를 보고 목적지에서 reassmble한다.

## 문제

1. link state 알고리즘과 distance vector 알고리즘이 사용하는 최단경로 알고리즘은 무엇인가요?
2. forwarding table은 어떻게 만드나요?
