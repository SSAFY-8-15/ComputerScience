노션
https://aerial-cap-9df.notion.site/3-TCP-UDP-00d56daa9d404e448a5e0f496f7ac529


# TCP

TCP는 Transmission Control Protocol의 약자이다.

TCP는 네트워크 계층 중 **전송 계층**에서 사용하는 프로토콜로서, 장치들 사이에 논리적인 접속을 성립하기 위하여 연결을 설정하여 **신뢰성을 보장하는 연결 지향 프로토콜**이다. 연결 지향이란, 통신을 시작하기 전에 원본 컴퓨터와 대상 컴퓨터 사이에 연결을 설정한다는 것을 의미한다.

TCP는 네트워크에 연결된 컴퓨터에서 실행되는 프로그램 간에 **일련의 옥텟(데이터, 메세지, 세그먼트라는 블록 단위)를 `안정적`으로, `순서대로`, `에러없이` 교환**할 수 있게 한다.



3 & 4방향 핸드 셰이크, 플로우, 오류 및 혼잡 제어를 사용하므로 신뢰성이 높다. 원본 컴퓨터에서 보낸 데이터가 대상 컴퓨터에서 정확하게 수신되는지 확인한다. 수신 된 데이터가 올바른 형식이 아닌 경우 TCP는 데이터를 재전송한다.

### [3 & 4 way handshake]

**3 way handshake - 연결 성립**

TCP는 정확한 전송을 보장해야 한다. 따라서 데이터를 주고받기에 앞서, 논리적인 접속을 성립하기 위해 3 way handshake 과정을 진행한다.

![https://media.geeksforgeeks.org/wp-content/uploads/TCP-connection-1.png](https://media.geeksforgeeks.org/wp-content/uploads/TCP-connection-1.png)

1. 클라이언트가 서버에게 SYN(SYNchronization) 플래그를 보낸다. (sequence: x)
2. **P: Q야 통신하자(SYN)**
3. 서버가 SYN(x)을 받고, 클라이언트로 받았다는 신호인 ACK(ACKnowledgement) 와 SYN 플래그를 보낸다. (sequence: y, ACK: x + 1)
4. **Q: 잘 받았어(ACK) 통신하자(SYN)**
5. 클라이언트는 서버의 응답으로 ACK(x + 1)와 SYN(y) 플래그를 받고, ACK(y+1)를 서버로 보낸다.
6. **P: 잘 받아써**

이렇게 세 번의 통신이 완료되면 연결이 성립된다.

**4 way handshake - 연결 해제**

연결 성립 후, 모든 통신이 끝났다면 해제해야 한다.

![https://media.geeksforgeeks.org/wp-content/uploads/CN.png](https://media.geeksforgeeks.org/wp-content/uploads/CN.png)

1. 클라이언트는 서버에게 연결을 종료한다는 FIN(FINish) 플래그를 보낸다.
2. **P: 그만하자(FIN)**
3. 서버는 FIN을 받고, 확인했다는 ACK를 클라이언트에게 보낸다. 이 때 모든 데이터를 보내기 위해 TIME OUT 상태가 된다.
4. **Q: 알겠어(ACK) 잠깐만 있어봐 (TIME OUT)**
5. 데이터를 모두 보냈다면, 연결이 종료되었다는 FIN 플래그를 클라이언트에게 보낸다.
6. **Q: 마저 다 보냈어. 그만하자(FIN)**
7. 클라이언트는 FIN을 받고, 확인했다는 ACK를 서버에게 보낸다. 아직 서버로부터 받지 못한 데이터가 있을 수 있으므로 TIME_WAIT을 통해 기다린다.
8. **P: 알게써(ACK) 잠만 있어바(TIME OUT)**
9. 서버는 ACK를 받은 이후 소켓을 닫는다. (closed)
10. TIME_WAIT 시간이 끝나면 클라이언트도 소켓을 닫는다. (closed)

이처럼 네 번의 통신이 완료되면 연결이 해제된다.

### 데이터 전송에 TCP를 사용하는 프로토콜

- HTTP (하이퍼 텍스트 전송 프로토콜),
- HTTPs (Hypertext Transfer Protocol Secure),
- FTP (파일 전송 프로토콜),
- SMTP (Simple Mail Transfer Protocol) 등

# UDP

UDP는 User Datagram Protocol의 약자이다.

전송 계층에서 사용되는 **비 연결형 프로토콜**이다. 연결을 설정하거나 대상 컴퓨터가 수신 준비가되었는지 여부를 확인하지 않으며 데이터를 직접 전송한다. UDP는 더 **빠른 속도**로 데이터를 전송하는 데 사용된다. **신뢰성이 떨어지며** 오디오 및 비디오 파일과 같은 데이터를 전송하는 데 사용된다.

UDP는 데이터 전달을 보장하거나 손실 된 패킷을 재전송하지 않는다.****

### 데이터 전송에 UDP를 사용하는 프로토콜

- DNS
- NFS
- RIP

# TCP와 UDP 차이

두 프로토콜은 모두 패킷을 한 컴퓨터에서 다른 컴퓨터로 전달해주는 `IP 프로토콜`을 기반으로 구현되어 있지만, 서로 다른 특징을 가지고 있다.

1. TCP는 Connection 지향이며, UDP는 Connectionless 프로토콜이다.
2. TCP는 전송 된 정보의 확인을 위해 유용한 데이터를 전송할 때 높은 신뢰성을 제공한다. 그리고 손실 패킷이있는 경우이를 다시 보낸다. UDP의 경우 패킷이 손실되면 재전송을 요구하지 않고 대상 컴퓨터가 손상된 데이터를 수신한다. 따라서 UDP는 신뢰할 수없는 프로토콜이다.
3. TCP는 데이터를 전송하기 전에 TCP가 연결을 설정하고 패킷의 적절한 전달을 보장하므로 UDP와 비교할 때 속도가 느리다. 반면에 UDP는 전송 된 데이터가 수신되었는지 여부를 확인하지 않는다.
4. UDP의 헤더 크기는 8 바이트이며 TCP의 헤더 크기는 두 배 이상이다. TCP 헤더 크기는 20 바이트이므로 TCP 헤더에는 옵션, 채우기, 체크섬, 플래그, 데이터 오프셋, 확인 번호, 시퀀스 번호, 원본 및 대상 포트 등이 포함된다.
5. TCP와 UDP는 모두 오류를 검사 할 수 있지만 TCP만이 정체와 흐름 제어를 모두 가지고 있으므로 오류를 수정할 수 있다.

|TCP|UDP|
|---|---|
|Connection-oriented protocol(연결지향형 프로토콜)|Connection-less protocol(비 연결지향형 프로토콜)|
|Connection by byte stream(바이트 스트림을 통한 연결)|Connection by message stream(메세지 스트림을 통한 연결)|
|Congestion / Flow control(혼잡제어, 흐름제어)|NO Congestion / Flow control(혼잡제어와 흐름제어 지원 X)|
|Reliable data transmission(신뢰성 있는 데이터 전송 - 안정적)|Unreliable data transmission(데이터 전송 보장 X)|
|Ordered, Lower speed(순서 보장, 상대적으로 느림)|Not ordered, Higer speed(순서 보장되지 않음, 상대적으로 빠름)|
|TCP packet : Segment(세그먼트 TCP 패킷)|UDP packet : Datagram(데이터그램 UDP 패킷)|
|HTTP, Email, File transfer에서 사용|DNS, Broadcasting(도메인, 실시간 동영상 서비스에서 사용|
|일 대 일(Unicast) 통신|일 대 일, 일 대 다(Broadcast), 다 대 다(Multicast) 통신|



---
문제

1. TCP와 UDP에서 사용하는 데이터 전송 단위는?
2. TCP에서 데이터를 주고받기 전에 먼저 서로 연결을 한다. 이때 연결 성립을 위해 사용하는 방식은?
