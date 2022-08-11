# Application Layer

- 프로세스 간의 통신 주관
- 프로세스 간 메시지를 주고 받는 용도인 Socket으로 연결 -> IP address & Port Number
- 컴퓨터 네트워크의 존재 이유.
- end system에만 존재한다.

## 구조

1. Client - Server : 서버와 클라이언트 간 통신

- 서버 : always-on, permanent IP address
- 클라이언트 : dynamic IP address

2. Peer to Peer : 호스트끼리 직접 통신하는 것

## Application이 하위 계층에서 받아야 할 서비스

1. Data Integrity : 데이터의 신뢰성 보장

- Transport Layer에서 제공

2. Throughput

- 1초에 n양이 도달해야하는 정도 확보 필요

3. Timing

- Packet이 적어도 어느 한 시점에는 도달할 수 있도록 해야 함

## HTTP

- Application Layer의 프로토콜
- HyperText Transfer Protocol
- TCP를 통해 서버에 연결된다.
- 서로 다른 end system에서 수행되는 프로그램끼리 서로 HTTP 메시지를 교환하여 통신한다.
- 프로그램끼리 어떻게 요청하고 전송하는지 정의해둔다.

### 역할

- request : hypertext 파일 요청
- response : 해당 파일 전달

### 특징

- Stateless

  - 서버는 이전 요청에 대한 상태를 기억하지 않음
  - 아무것도 기억하지 않아 상태가 없음

### Connections

- non-persistent : 한 연결에 한 정보만 전달 후 연결 종료 (10개 -> 10연결)
- persistent : 한 연결에 모든 정보 전달. 정보 하나가 지나가도 모든 정보가 올 때까지 연결은 지속된다. (10개 -> 1연결)

## Socket

- 프로세스 간의 통신 방식
- 여기에서 통로 역할을 한다.
- app과 network 사이의 인터페이스
- OS 간의 인터페이스
- Transport 방법에 따라 종류가 나뉜다.
  - TCP = SOCK_STREAM
  - UDP = SOCK_DGRAM

## APP

| app                    | application layer protocol | underlying transport protocol |
| ---------------------- | -------------------------- | ----------------------------- |
| e-mail                 | SMTP                       | tcp                           |
| remote terminal access | telnet                     | tcp                           |
| web                    | HTTP                       | tcp                           |
| file transfer          | FTP                        | tcp                           |
| streaming              | HTTP, RTP                  | tcp or udp                    |
| internet telephony     | SIP, RTP                   | tcp or udp                    |

---

## 문제

1. Application의 대표적 프로토콜은?
2. 소켓의 주소를 알기 위해 필요한 정보 두가지
3. HTTP의 특징에 대해 설명하세요.
