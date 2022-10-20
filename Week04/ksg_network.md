# 네트워크와 인터넷, IP의 개념

### 네트워크란?
- 둘 이상의 컴퓨터가 통신 기술을 이용하여 서로 연결되어 있을때, 이때의 컴퓨터간 통신 링크들을 네트워크라 한다.


### 네트워크의 종류 
- LAN (Local Area Network) : 근거리 네트워크
		가정 및 사무실과 같은 작은 지리적 영역에 제한된 컴퓨터 네트워크
- WAN( Wide Area Network ) : 광역 네트워크
		넓은 지역에 분산 된 컴퓨터 네트워크를 말한다. 
	
	
### 인터넷과 인트라넷
- 인트라넷 : 특정 기업, 조직, 단체등에서 구성한 비교적 소규모의 네트워크로 폐쇄적인 네트워크로 인터넷과 망이 분리되어 있다. 프로토콜에 제약이 없다.

- 인터넷 : 전 세계에 연결되어 있는 거대한 컴퓨터 네트워크를 말한다. 국제  표준으로 정한 프로토콜 (TCP/IP 프로토콜)을 사용한다.
	
	
### ISP(Internet Service Provider)

- 인터넷에 접속 할 수 있는 수단을 제공하는 자를 말한다.
	
	ISP는 고유한 망식별번호(ASN)을 가진다.
	
	ISP는 네트워크를 계층적으로 구성한다. 
	
	- Tier 1 ISP (International ISP) : 대륙, 국가와 같은 레벨의 초대형 ISP, 여러개의 Tier 2 ISP간 네트워크로 이루어져있음.
	- Tier 2 ISP (Domestic ISP): 대단위, 대도시, 광역시/도 단위의 대형 ISP,
	- Tier 3 ISP : 마지막 단계의 ISP로 실제 가정, 기업등에 연결되는 ISP에 해당. Local ISP라고도 한다.

### 라우팅과 포워딩

	
### IP address
- IPv4 : 32bit의 주소로 0.0.0.0~255.255.255.255로 표현된다.
- IPv6 : 128bit의 주소로 0:0:0:0:0:0:0:0 ~ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff로 표현된다.

	aaaa:0:0:104d:dddd:eeee:ffff:1034 에서 0은 생략 가능하므로 aaaa::104d:dddd:eeee:ffff:1034와 같이 표현 할 수 있다.



### 서브넷

- IP는 구분하기 쉽게, 마치 트리 구조와 같이 상위 네트워크와 하위네트워크로 계층화 할 수 있는데, 이때의 하위 네트워크를 상위 네트워크의 서브넷이라고 한다.  서브넷은 아이피의 앞쪽 특정 영역을 공유한다.

#### 서브넷 마스크 
	
- 서브넷은 자신의 ip와 서브넷 마스크를 and연산한 결과가 상위 네트워크의 주소를 따르도록 한다.

- 예를 들면, 110.251.12.3 의 subnet mask가 255.0.0.0이면 해당 호스트는 network prefix가 110.0.0.0인 네트워크의 서브넷에 속해있다고 할 수 있다. 

#### Classless Inter-Domain Routing (CIDR)
- 아이피 주소를 할당하고 패킷을 라우팅하는 방법으로 기존의 IP Class를 대체한다.
- IP를 계층화하며, 특정 길이의 공통 접두어를 상위네트워크로 정의한다. 
- A.B.C.D/E 와 방식으로 쓰며, 이때 E를 접두어 길이를 의미한다. 즉, 서브넷 마스크에서 연속된 1의 개수를 지칭한다.


### 사설망, NAT / Private IP Address

#### 사설망
인터넷 가입자가 많아 짐에 따라 IP주소 고갈 등의 문제를 해결하기 위해 하나의 네트워크내 여러 호스트가 하나의 공인아이피(public ip)를 공유하는 사설망(private network)가 등장하였다.

#### 공인 아이피 / 사설 아이피
공인 아이피(Public IP)는 실제 인터넷에서 직접 식별 할 수 있는 IP주소를 말한다. 

사설 아이피(Private IP)는 DHCP 서버에 의해 배정받은 아이피로 외부에서 식별할 수 없다.

#### DHCP / DHCP 서버
Dynamic Host Configuration Protocol의 약자로, 사설망내 사설 IP의 관리, 할당(임대), 반납을 수행할 목적으로 고안된 프로토콜 이다. 실제 사설 IP관리는 DHCP 서버에 의해 수행된다.



#### NAT(Network Address Translation)
사설망내 호스트가 외부 네트워크와 통신하기 위해서는 외부 네트워크가 자신을 식별할 수 있도록 해야 하는데, 이때 NAT를 통해 자신의 사설 아이피를 공인아이피로 변환한다. 

외부 망의 입장에서는 사설망내 서로 다른 호스트들을 포트번호(port)를 통해 구분한다.


# Network Layer

### Network Layer의 목적
- 한 네트워크에서 다른 네트워크로의 데이터 전송을 목적으로 한다.


### Network Layer의 역할

- 포워딩
- 라우팅
- 멀티플렉싱/ 디멀티플렉싱
- 오류제어

### 포워딩과 라우팅
 - 포워딩 : 하나의 라우터에서 다른 라우터로 패킷을 전송하는 작업

 - 라우팅 : 연결된 여러개의 라우터중 어떤 라우터로 보내야 하는지 결정하는 작업

### Network Layer Protocol Suite:
- 라우팅 프로토콜 : RIP, OSPF, BGP 
- 인터넷 제어 프로토콜 : ICMP
- 인터넷 프로토콜 : IP
	

## Internet Protocol(IP)

### 패킷의 구조

[ver | head_len | type_of_service | length]
[identifier | flag | fragment offset]
[TTL | upper layer | checksum ]
[ sourrc ip ]
[ destination ip ]
[ options ]
[ data ]

- ver : IP Protocol의 버전을 뜻한다. 
- head_len : 헤더의 총길이를 뜻한다. 기본적으로 20byte지만, IPv6를 사용하는 경우 늘어난다.
- identifier, flag, fragment offset : fragmentation과 reassembly과정에 사용된다.
- TTL : Time To Live로 패킷이 영원히 루프하여 오버헤드를 발생시키는 경우를 방지하기 위해 도입되었으며, 1 hop당 ttl이 1씩 감소된다. TTL이 0이 되면, 해당 패킷은 수신시 버려진다.

### fragmentation, reassembly
IP 패킷의 데이터양이 길어지는 경우 해당 패킷을 여러개로 쪼개어 보낼 수 있도록 한다. 

데이터를 나누는 작업을 fragmentation이라 하며, 합치는 작업을 reassembly라고 한다.



## 라우팅 알고리즘



### 라우팅 알고리즘의 구분
- 중앙집중형 vs 분산형 : 모든 비용 정보를 다 알고있는가 or 자신과 연결된 노드들의 정보만 알고 있는가

- 정적 라우팅 vs 동적 라우팅 : 라우팅 경로가 결정시 해당 경로로만 보내는가? or 네트워크 부하를 고려하여 라우팅 경로를 수시로 변경 할 수 있는가?


### 링크 상태 라우팅 알고리즘
- 연결된 모든 네트워크로의 전송 비용이 알려져있을때 사용가능하다.
- 중앙 집중형 알고리즘에 속한다.
- 다익스트라 알고리즘을 사용한다.

### 거리 벡터 알고리즘
- 연결된 모든 네트워크의 전송 비용이 수시로 바뀌는 경우 사용한다.  
- 분산형 알고리즘에 속한다. 

- 벨만-포드 equation을 통해 dynamic하게 갱신한다.
- 자신이 계산한 distance vector와 이웃한 라우터의 distance vector를 교환함으로써 갱신한다.

### 플루딩 라우팅
- 자신에게 패킷을 보낸 라우터를 제외한 다른 모든 라우터에게 패킷을 복사하여 전달한다.
- 단순하지만 패킷 전송의 비용이 크다.

### 경로 벡터 라우팅
- 거리 대신 경로를 기반으로 라우팅을 한다. 즉, 라우터간 최적 거리가 아닌, 최적인 상황에서의 경로 정보를 사용한다.

- 거리벡터 라우팅과 다르게 Looping이 일어나지 않는다. 

- 거리 벡터에 비해 벡터 정보가 거대하므로 advertising시 오버헤드가 크다.

Looping이란? (한 시스템이 고장났을 경우 패킷 라우팅이 꼬여서 특정 패킷이 목표에 도달하지 못하고 영원히 루프되는 현상)


## Routing Protocol

### Autonomous System
이 세상에 존재하는 라우터를 전부 식별하는 것은 불가능하기 때문에,  모든 라우터는 자신과 직접 연결된 라우터 (Neighbor)와 자신이 속한 라우터 망(AS, Autonomous System)내 라우터 만을 식별하여 전송하는 방식을 쓴다.

대신에, 서로 다른 AS간 서로를 식별할 수 있도록 

라우팅알고리즘은 크게 IRP, ERP로 나뉘게 된다.

- IRP(Interior Routing Protocol) : 내부 라우터 망내에 라우팅을 담당한다. 
- ERP(Exterior Routing Protocol) : 서로 다른 AS 사이 경계선에서 라우팅 정보를 교환하는데 사용되는 프로토콜

#### RIP( Routing Information Protocol)
- 거리 벡터 알고리즘을 사용할때, 거리 정보를 갱신하기 위해 정보를 교환하는 프로토콜, IRP 프로토콜이다.
- 매 주기(30초) 마다 연결된 라우터로의 advertising을 통해 송신이 된다. 
- 라우터간 해당 정보를 전달하는 길이는 최대 15 hop으로 제한한다.(TTL과 같은 개념)
- 전송되는 데이터 : (시작지점과 목적지점, Distance Vecter)

#### OSPF (Open Shortest Path First) 
- 링크 상태 라우팅 알고리즘을 사용할때  쓰이는 프로토콜로 IRP 프로토콜이다.
- 이웃 라우터간 자신의 링크 정보를 교환한다. (Link-State-Advertisement), 
- Neighbor Table (모든 인접 라우터들의 리스트) 및 Link State Database(소속 망에 존재하는 모든 네트워크 토폴로지로의 비용정보) 를 갱신한다.

 #### BGP(Border Gateway Protocol)
- ERP 프로토콜에 해당한다. 현재 표준으로 정한 ERP 프로토콜중 유일하다.
- Path Vector 알고리즘을 사용한다.

- eBGP : peer AS간 BGP 메세지를를 교환한다. 

- iBGP : eBGP를 통해 얻은 결과를 내부 AS에 전파한다.


## Internet Control Message Procotol (ICMP)

- 라우터간 상태 및 정보를 교환하기 위한 프로토콜이다
- 타입 및 코드로 분류되어 있다. 

### ICMP message 의 type 예시

  0     : Echo Reply              
  3     : Destination Unreachable
  5     : Redirect
  6     : Alternate Host Address    
  8     : Echo                      
 30    : Traceroute



## 문제
1. 포워딩과 라우팅의 개념을 설명하시오.
2. IP프로토콜에서 TTL(Time to live)를 사용하는 이유를 설명하시오. 