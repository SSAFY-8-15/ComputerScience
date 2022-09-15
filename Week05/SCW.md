
인터넷 브라우저에 주소창에 url을 입력한 후 발생하는 일

1. **브라우저의 URL 파싱**
    
    브라우저는 입력받은 URL의 구조를 해석한다. 어떤 프로토콜로, 어느 도메인으로, 어떤 포트로 보낼지 해석하게 됨.
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a9459808-3a2c-4613-85ef-c647952bc252/Untitled.png)
    
    - 어떤 프로토콜로 해당 URL에 요청할 것인지
    - 어떤 URL로 요청할 것인지
    - 어떤 포트로 요청할 것인지
    
    default port : HTTPS - 443 / HTTP - 80
    
2. **HSTS 목록 조회**
    
    HSTS = HTTP Strict Transport Security
    
    HTTP 허용하지 않고 HTTPS  사용하는 연결만 허용하는 기능.
    
    만약 HTTP로 요청이 왔다면 HTTP 응답헤더에 STS라는 필드포함하여 응답하고 이를 확인한 브라우저는 해당 서버에 요청할 때 HTTPS만을 이용하여 통신하게 됨. + 자신의 HSTS캐시에 해당 URL 저장하고 이를 HSTS목록이라고 함.
    
    브라우저는 HSTS목록을 조회하여 해당 요청을 HTTPS로 보낼지 판단. 목록에 URL이 존재한다면 HTTP 요청한다해도 HTTPS로 요청함
    
3. **URL → IP주소로 변환**
    
    단순 URL주소로는 컴퓨터끼리 통신 불가능, IP주소로 변환필요.
    
    브라우저는 자신의 로컬 hosts파일과 브라우저 캐시에 해당 URL존재하는지확인. 존재X→도메인주소를 IP로 변환해주는 DNS서버에 요청하여 URL을 IP주소로 변환
    
    *[ DNS 서버 요청과정 ]*
    
     (1) 미리 설정 된 Local DNS에 해당 URL 주소의 IP주소를 요청
    
     (2) Local DNS에 해당 IP주소가 존재한다면 이를 응답하고, 없다면 다른 DNS 서버와 통신. root DNS 서버에 해당 URL의 IP주소를 요청
    
     (3) root DNS서버에 해당 IP주소가 없다면 하위 DNS 서버에 요청하라고 응답. 이 응답을 받은 Local DNS는. net 도메인을 관리하는 DNS 서버에 같은 내용을 요청
    
     (4) .net DNS 서버에 해당 IP주소가 없다면 하위 DNS 서버에 요청하라고 응답. 이 응답을 받은 Local DNS는 [daum.net](http://daum.net/) 도메인을 관리하는 DNS 서버에 같은 내용을 요청
    
     (5) [daum.net](http://daum.net/) DNS 서버에서 IP주소를 응답받은 Local DNS는 해당 IP주소를 캐싱하고 응답
    
4. **라우터를 통해 해당 서버 게이트웨이까지 이동**
    
    DNS에서 받은 IP주소로 해당서버에 요청보냄. 라우터의 라우팅을 이용하여 요청을 보내게된다
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/18c7d6f7-35bf-416a-9be7-5cc722bbc6ec/Untitled.png)
    
    라우터의 라우팅 테이블을 통해 해당 요청이 어떤 경로를 가야할지 지정
    
5. **ARP를 통해 IP주소를 MAC주소로 변환**
    
    실질적인 통신을 하기 위해서는 논리 주소인 IP주소를 물리 주소인 MAC 주소로 변환해야 합니다. 이를 위해 해당 네트워크 내에서 ARP를 브로드 캐스팅. 해당 IP주소를 가지고 있는 노드는 자신의 MAC 주소를 응답.
    
6. **대상 서버와 TCP소켓 연결**
    
    대상 서버와 통신하기 위해 TCP 소켓 연결을 진행, 소켓 연결은 3-way-handshake 과정을 통해 이루어짐.
    
    지금 하는 요청은 HTTPS 요청이기 때문에 서로 암호화 통신을 위한 TLS 핸드쉐이킹이 추가됨. 이를 통해 서버와 클라이언트는 암호화 통신 가능.
    
7. **HTTP(HTTPS) 프로토콜로 요청, 응답**
    
    연결이 확정되었으니 드디어 해당 페이지 **www.daum.net**
    를 달라고 서버에게 요청. 서버에서 해당 요청을 받고, 이 요청을 수락할 수 있는지 검사하고 서버는 이 요청에 대한 응답을 생성하여 브라우저에게 전달
    
8. **브라우저에서 응답 해석**
    
    HTML, CSS, Javascript 해석, 화면의 띄움
    
    Q. HTTPS 요청이기 때문에 서로 암호화 통신을 위한 (___) 핸드쉐이킹이 추가됨 <TLS>
    
    Q. URL 구조 3가지는 무엇인가요? <프로토콜,url,포트>
