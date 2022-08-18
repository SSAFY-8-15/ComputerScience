# Transport Layer

### Multiplexing / Demultiplexing

Multiplexing : 여러 프로세스에서 생성된 socket을 transport layer에서 segment로 묶어서 이동시킴

Demultiplexing : segment를 받아서 application으로 올려줄 때 분리해서 Socket으로 올려줌. 이때 어떤 Socket일지를 정하게 된다.

**Demultiplexing 방법**

헤더에 맨 앞에 number들로 한다.

UDP : source port #, destination port # 두 가지

→ length, checksum 까지 네가지로 에러 체크까지 해준다.

TCP : destination IP & port #, Source IP & port # 네 가지

→ 각 client마다 소켓을 관리한다.

## TCP

- point-to-point : 프로세스 한쌍끼리 통신을 책임진다. 연결 하나당 프로세스 두개!
- reliable, in-order byte stream
- pipelined : 한꺼번에 쏟기, congestion & flow control → window size 결정
- send & receive buffers
  - sender buff : 재전송하기 위해 저장해두는 곳
  - receiver buff : 비순서로 오는 것을 저장해두는 곳
- full duplex data : 양방향으로 진행된다. S,R 역할이 정해진 것이 아님
  → 즉, sender buff, receiver buff 두개씩 갖고 있다.
- connection-oriented : handshaking
- flow controlled : sender will not overwhelm receive, Receiver가 받을 수 있는 양만큼 받아주기

### **Structure**

- source port # (16bits) : 보내는 사람 ID
- dest port # (16bits) : 도착지 ID

→ header 부분 : 작아야 한다. 크면 overhead 이다.

⚡️ 각 layer의 전송 단위 : 모두 header과 data 부분이 있다.

### TCP seq # and ACK

- Seq # : data의 가장 앞 byte를 이용 한다.
- ACK # : 다음 차례때 받아야 할 데이터 시작 #을 상대방에게 피드백으로 알리는 것

→ Sender는 본인의 Seq#을 만들어서 관리해야한다.

→ Receiver는 상대방의 Seq#을 기다리고 이를 tracking하고 있다. 이에 맞춰서 ACK을 보낸다.

### Timeout

1. timeout 을 RTT 로 정하자 → 하지만 상황에 따라 다르긴 해서 안됨.
2. EstimatedRTT로 하자 : 약간의 보정값이 포함 됨 (상황을 가정하고 보정값)

→ 그래도 천차만별이라 유실이 아니어도 유실처리해서 안된다.

1. DevRTT 로 마진값을 붙이자 ⇒ Timeout Interval

### Reliable data transfer

- pipelined segments
- cumulative ACKs
  → ACK이 가다가 loss가 되어도 다음 도착하는 pkt까지 누적해서 ACK을 보내게 되어 Loss 된 것도 처리가 가능해진다.
- using single retransmission trimer

→ GBN과 유사하지만 다른 점은 timer가 expire되면 모두 재전송하는 것

### Flow Control

Sender는 Receiver의 buffer 안의 Available Space에 맞춰서 데이터를 보내야 한다.

이는 Receiver가 피드백을 할 때 Segment의 header에 담겨서 간다.

→ 계속 알려주기 때문에 Flow Control이 가능하다.

하지만 ACK을 보낼 때만 가능하다. Avail하지 않다는 패킷이 와서 Sender가 보내는 것을 중단하면 Avail해져도 Receiver는 이를 알릴 방법이 없다.

→ Sender는 공간이 없다는 피드백 이후 주기적으로 찔러서 확인해줘야 한다.

### Handshake

1. 3-way handshake : 초기 연결을 위한 단계

   서로의 seq# 등 부가정보를 알아둘 필요가 있기에 필요한 단계이다.

   1. Client → Server : SYN msg (control segment임)
      - TCP Connection을 열고자 할 때 전송한다.
      - header의 SYN bit이 1인 상태, 데이터 X
      - 본인의 Seq# 도 같이 보낸다.
   2. S → C : SYNACK msg
      - 연결에 승낙하기 위해 전송
      - header의 SYN bit이 1인 상태, 데이터 X
      - 본인의 Seq# 와 ACK를 보낸다.
   3. C → S : ACK
      - 더이상 SYN bit이 1이 아니다. 데이터도 담겨 있다.
      - 이 과정이 있는 이유는 2번에 대한 피드백으로, 없다면 Server는 확신을 갖지 못한다
      - 이것이 와야만 S는 buffer을 만든다.
      - 이 부분은 HTTP Req이기도 하다.

2. 4-way handshake : 종료하는 단계

   연결을 끊는 과정

   1. C → S : FIN
   2. S → C : ACK
   3. S → C : FIN
   4. C → S : ACK

      이후로 C는 timed wait을 둔 뒤 종료한다.

      - S가 보낸 데이터가 덜 도착했을 수도 있고
      - 만약 없다면 ACK이 유실돼버리면 S는 FIN을 지속적으로 보내지만 응답은 지속적으로 없는 딜레마가 생긴다.

### Congestion Control

- Sender가 안막히게 본인이 조절해야 함 → 자기 자신을 위함
  - 막히면 본인에게 안 좋은 것이므로 직접 행동하게 되는 것
- 독립적인 동작이지만 결국은 서로를 생각하게 됨

**🤔  막히는 것은 어떻게 알까 - 누가 정보를 주냐에 대한 관점**

1. Network-assisted : 라우터가 피드백 줌 → 사용하지 않음. 라우터는 본인 일도 바쁨
2. End-End
   - 명시적인 피드백이 아니라 Sender가 유추하는 것
   - Loss나 Delay를 통해 추론한다.

**#️⃣  3 main phases**

1. Slow Start : 조금씩 작은 양으로 시작 (네트워크 상황을 모르기 때문에)

   → 증가 속도는 매우 빠름

2. Additive increase : threshold를 지나면 linear하게 증가함

   → 증가 속도는 느림

3. Multiplicative decrease

   pkt loss, delay를 감지하면 전송 속도를 1/2한 후 다시 2의 과정을 거친다.

⇒ 보내는 양 자체는 window size이다. 이것을 조절하게 된다.

> Window Size : 1MSS ( Max Segment Size로 조절 단위 를 뜻함 ) = CongWin

전송 속도는 Window Size가 영향을 가장 많이 준다.

속도를 조절한다는 것은 내 행동에 따라 결정되는 것.

→ 독립적이지만 은연 중에 서로에게 영향을 주게 된다.

**#️⃣  Refinement**

1. TCP Series 1 **Tahoe**
   1. Slow Start → threshold
   2. → Additive Increase → Loss or Delay
   3. Threshold를 현재 막히게 된 지점의 양의 1/2로 설정 → 다시 Slow Start

⇒ TCP는 동일하게 보지만, 네트워크 상 “패킷 유실"은 관점이 다르다.

1. Time out ⇒ 패킷 몽땅 안 간 경우
2. 3 duplicate ACKs ⇒ 하나만 안간 것

→ 조금 다른 현상으로 다르게 반응 해야 함. 그래서 2번이 나오는 것

1. TCP Series 2 **Reno**
   - 차이를 인지하고 다르게 대응함
   1. Time out이면 Tahoe와 동일하게 대응
   2. 3 dup ACKs이면 전송량만 1/2로 바꾼다.

**⚡️ TCP는 공평한가?**

- 독립적으로 congestion control하지만 공평하게 나누어 갖는다.
- Congestion control을 하다보면 1/2씩 줄어들고 늘고를 반복하여 중앙지점에 도달함

하지만 TCP connections 끼리 공평한거지 사용자로 따지면 아니다.

한 사용자가 여러 TCP를 가진다면 한 사용자에게 치우치게 되는 것

## UDP

- 비연결 지향적 프로토콜: 데이터를 주고받을 때 연결 절차를 거치지 않고 발신자가 일방적으로 데이터를 발신하는 방식

### UDP의 단점

- 데이터의 신뢰성이 없다.
- 의미있는 서버를 구축하기위해서는 일일이 패킷을 관리해주어야 한다.

### UDP의 특징

- 비연결형 서비스로 연결 없이 통신이 가능하며 데이터그램 방식을 제공한다.
- 데이터 경계를 구분한다. (데이터그램(datagram) 서비스)
- 정보를 주고 받을때 정보를 보내거나 받는다는 신호절차를 거치지 않는다.
- 신뢰성 없는 데이터를 전송한다. (데이터 재전송과 데이터 순서 유지를 위한 작업을 하지 않는다.
- 패킷관리가 필요하다.
- 패킷 오버헤드가 적어 네트워크 부하가 감소되는 장점.
- 상대적으로 TCP보다 전송속도가 빠르다.

## 문제

1. TCP 연결을 종료할 때의 절차의 이름은?

2. TCP 방식의 ACK의 의미는?
