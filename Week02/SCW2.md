
(7계층 Application Layer 응용 계층)

응용 프로그램과 통신 프로그램 간의 인터페이스를 제공

HTTP라는 응용계층 프로토콜은 응용 프로그램인 웹(Worldwide Wed) 브라우저(browser)에게 필요한 데이터를 송수신할때 사용한다.

대표적 프로토콜: 원격 접속을 위한 텔넷(Telnet), 파일전송을 위한FTP, 도메인 이름을 IP 주소로 변환시켜주는 DNS, 메일전송을 위한 프로토콜인 SMTP등

7계층 응용계층 서비스들은 고유의 포트번호를 가지고 있으나 절대적인것은 아니며 관리자들이 변경가능

![https://blog.kakaocdn.net/dn/btj25o/btqwtREcica/gkPKDDc2BR78uJRvLIhwC0/img.png](https://blog.kakaocdn.net/dn/btj25o/btqwtREcica/gkPKDDc2BR78uJRvLIhwC0/img.png)

Layer 6. 표현 계층(Presentation Layer)

표현 계층에서는 응용 계층으로부터 전달받은 데이터를 읽을 수 있는 형식으로 변환.

응용 계층의 부담을 덜어주는 역할. 응용 계층으로부터 전송받거나 응용 계층으로 전달해야 할 데이터의 인코딩과 디코딩 이루어짐.

표현 계층은 데이터를 안전하게 사용하기 위해서 암 / 복호화 진행.

ex)

유니코드(UTF-8)로 인코딩 되어있는 문서를 ASCII로 인코딩 된 문서로 변환하려 할 때

이 계층에서 변환이 이루어짐

대표적 프로토콜들 : ASCII, MPEG, JPEG, MIDI, EBCDIC 등

덜 대표적 프로토콜들 : XDR, AFP, PAP 등
Layer 5. 세션 계층(Session Layer)

이 계층에서는 두 컴퓨터 간의 대화나 세션을 관리합니다.

모든 통신 장치 간에 연결을 설정, 관리 및 종료하고

또한 연결이

전이중(Full duplex / 양방향)인지 반이중(half duplex / 단방향)인지

여부를 확인하고 체크 포인팅과 유휴, 재시작 과정 등을 수행하며

호스트가 갑자기 중지되지 않고 정상적으로 호스트를 연결하는 데 책임이 있다.

이 계층에서는 TCP/IP 세션을 만들고 없애고

통신하는 사용자들을 동기화하고 오류 복구 명령들을 일괄적으로 다루며

통신을 하기 위한 세션을 확립, 유지, 중단 하는 작업을 수행

그리고 위에 작업들은 운영체제가 실시

대표적 프로토콜들 : NetBIOS, SAP, SDP, PIPO, SSH, TLS 등이 있고

RPC(Remote Prodcedure Call) : 별도의 원격제어 위한 코딩 없이 다른 주소 공간에서 함수나 프로시저 실행할 수 있는 프로세스 간 통신에 사용되는 프로토콜

NetBIOS: 응용프로그램에게 API 제공하여 상호 통신할 수 있도록 해주는 프로토콜

덜 대표적 프로토콜들 : NWLink, ASP, ADSP, ZIP DLC 등

-웹(Worldwide Wed) 브라우저(browser)에게 필요한 데이터를 송수신할때 사용하는 프로토콜은? : HTTP

-DDNS(동적DNS)에 관해 설명하시오.

도메인의 IP가 유동적인 경우 사용된다. ip가 바뀌어도 DDNS로 설정한 도메인값은 변하지 않기 때문에 용이하게 접속가능하다.

일반적으로 우리가 이용하는 포털사이트나 각 기업, 정부기관의 홈페이지 들은 해당 기업이나 기관 등이 소유한 고정 IP를 통해서 DNS 주소를 할당 받기 마련인데, 가정 단위에 있어서 고정 IP를 할당받는 것은 상당한 비용이 들 뿐더러 IP 추적에 의한 사생활 침해 요소가 있기 때문에 유동 IP를 사용하게 된다. 그런데 유동 IP 에 그냥 DNS 주소를 할당해 버리면 사용자의 IP가 바뀌기 전 까지는 멀쩡히 작동하지만, IP 유동이 일어나는 순간 해당 주소로 들어온 트래픽은 본래 그 주소를 할당받은 사용자에게 가지 않고 새로이 그 IP를 차지하게된 엉뚱한 사용자에게 가게된다. 이를 극복하기 위해 나온것이 바로 DDNS이며 일반적으로는 유동 IP로 인터넷을 공급받는 대다수의 인터넷 사용자들이 개인 서버나 NAS 구축을 하려 할때 이용하게 된다

-Duplex의 2가지 방식에 대해 간략히 설명하시오.

half d : 반 이중방식, 데이터 송신하는 동안 데이터를 수신하지 못하는 방식. (무전기st)

full d: 전 이중방식, 통신하는 쌍방 모두 데이터 송신, 수신할 수 있음.
