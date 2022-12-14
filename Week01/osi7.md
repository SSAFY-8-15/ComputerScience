# OSI 7계층

## OSI 7계층이란?
OSI는 Open Systems Interconnection의 줄임말로 ISO(국제표준화기구)가 1984년에 발표했다.




통신이 일어나는 과정을 크게 7단계로 계층화하여 구분하였다.

## OSI  계층구조

- Physical Layer
- Data Link Layer
- Network Layer
- Transport Layer
- Session Layer
- Presentation Layer
- Application Layer

## OSI 계층 구조의 특징

1. 데이터 캡슐화 
	사용자 데이터가 각 계층을 지나면서 하위 계층은 상위 계층으로부터 온 정보를 데이터로 취급하며, 이에 덧붙여서 자신의 계층 특성을 담은 제어정보를 헤더화 시켜 붙이는 일련의 과정이다. 

2. 독립성 
	상위 계층은 고유한 책임을 지니며, 하위 계층의 정보나 형식에 의존하지 않는다. 


# OSI 계층별 특징

## Physical Layer

데이터의 단위 :
- 비트 

기능 :
- 전기/기계적 특징을 통해 물리적 매체간 데이터전송
- 인코딩(아날로그 신호->디지털 신호)
- 디코딩(디지털 신호->아날로그 신호)
- 전기신호의 증폭 및 변환

## Data Link Layer

데이터의 단위 : 
- 프레임

기능 : 
- 식별 : 고유한 네트워크 식별 주소인 Mac Address주소를 사용한다. 네트워크 장비간 Mac주소를 통해 식별 가능하도록 한다.
- 오류 감지 : 신호 전달과정에서 발생한 오류를 감지하고, 오류가 있는 데이터를 폐기한다.
- 다중 접속 : 주어진 시간, 주파수 등을 여러 사용자가 공동으로 사용할 수 있도록 하는 기술.


## Network Layer

데이터의 단위 : 
- 패킷

기능 : 
- 한 네트워크 에서 다른 네트워크로의 데이터 전송이 목적.
- IP Address로 네트워크를 구분한다.
- 라우팅 : 라우터간 통신 경로를 최적화하는 작업. (어디로 보내기 위해 어디를 거쳐야 하는가? 에 관한 문제)
- 오류 감지 기능 제공.

- 대표 프로토콜 : IP 프로토콜

## Transport Layer
데이터의 단위 : 
- 세그먼트

기능 : 
- 종단(네트워크에서 데이터 송수신이 일어나는 최종 사용자)간 데이터 전송이 목적
- Port로 구분한다.
- 멀티플렉싱 : 하나의 통신채널을 통해 두개 이상의 데이터를 보내는 작업.
- 디멀티플렉싱 : 멀티플렉싱에 의해 나눠진 데이터를 복원하는 작업, 식별자로 port번호가 사용된다.
- 오류 감지 기능을 제공한다.

- 대표 프로토콜 : TCP프로토콜, UDP프로토콜

## Session Layer
기능 :
- 양 끝단 응용 프로세스 간 세션(연결)관리. 세션이 유지되는 동한 동기화를 제공한다.

동기화 기법 :
- 전이중 통신 : 단말기간 데이터 송수신을 위해 독립회선을 사용
- 반이중 통신 : 한쪽이 송신하는 동안 다른 쪽에서 수신하는 통신으로, 전송 방향이 교체될 수 있다.

## Presentation Layer
기능 : 
- 사용자 시스템간 데이터 인코딩, 압축, 암호화등의 작업을 수행. 일종의 양 끝단 사용자간 데이터 송수신 과정에서 번역을 하는 것과 같다고 보면 된다.

대표 프로토콜 : TLS/SSL

## Application Layer
기능 : 
- 응용프로세스가 직접 데이터를 읽고 쓰는 영역이다. 최종 사용자에게 직접적으로 보여지는 부분에 해당한다.

대표 프로토콜 : HTTP, DNS, SSH, FTP, Telnet


## 연습문제
1. OSI 7계층을 상위 계층부터 하위 계층 순으로 모두 나열하라
2. Application Layer의 대표적 프로토콜 한개를 적어라
3. OSI 7계층중 종단간 데이터 통신을 보장하기 위한 목적을 지닌 계층은?
4. Data Link Layer에서 제공하는 기능중 Physical Layer에서 보장하지 않는 대표적인 기능을 적으시오
5. OSI 7계층중 양 끝단 프로세스간 동기화를 제공, 관리하는 목적을 지닌 계층은?