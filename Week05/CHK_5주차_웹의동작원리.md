노션 https://aerial-cap-9df.notion.site/5-349eebeddb564a36a3a24148b4b6ecfb
# #5. 웹의 동작 원리

# www.google.com을 주소창에 치면 발생하는 일


<img src="https://aerial-cap-9df.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F178ad742-4927-4208-a49b-ecc0c904f2a3%2FUntitled.png?table=block&id=37945afa-025d-427a-b38e-bcefac4b28cc&spaceId=54a976d5-bf03-458e-acc7-499adb0c8680&width=1450&userId=&cache=v2" width="800" height="800">

①② 사용자가 웹 브라우저를 통해 찾고 싶은 웹 페이지의 URL 주소를 입력함.

③ 사용자가 입력한 URL 주소 중에서 도메인 네임(domain name) 부분을 DNS 서버에서 검색함.

④ DNS 서버에서 해당 도메인 네임에 해당하는 IP 주소를 찾아 사용자가 입력한 URL 정보와 함께 전달함.

⑤⑥ 웹 페이지 URL 정보와 전달받은 IP 주소는 HTTP 프로토콜을 사용하여 HTTP 요청 메시지를 생성함.

이렇게 생성된 HTTP 요청 메시지는 TCP 프로토콜을 사용하여 인터넷을 거쳐 해당 IP 주소의 컴퓨터로 전송됨.

⑦ 이렇게 도착한 HTTP 요청 메시지는 HTTP 프로토콜을 사용하여 웹 페이지 URL 정보로 변환됨.

⑧ 웹 서버는 도착한 웹 페이지 URL 정보에 해당하는 데이터를 검색함.

⑨⑩ 검색된 웹 페이지 데이터는 또 다시 HTTP 프로토콜을 사용하여 HTTP 응답 메시지를 생성함.

이렇게 생성된 HTTP 응답 메시지는 TCP 프로토콜을 사용하여 인터넷을 거쳐 원래 컴퓨터로 전송됨.

⑪ 도착한 HTTP 응답 메시지는 HTTP 프로토콜을 사용하여 웹 페이지 데이터로 변환됨.

⑫ 변환된 웹 페이지 데이터는 웹 브라우저에 의해 출력되어 사용자가 볼 수 있게 됨.

<img src="https://aerial-cap-9df.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F9ecb49fe-a6f8-41e2-8772-d3fddb0d31f8%2FUntitled.png?table=block&id=df1ab1be-5a29-4c3c-bcff-cdd2783d6eda&spaceId=54a976d5-bf03-458e-acc7-499adb0c8680&width=1600&userId=&cache=v2" width="800" height="800">

## **1. www.google.com을 브라우저 주소창에 친다**

## **2. Browser는 캐싱된 DNS 기록들을 통해 www.google.com에 대응되는 IP 주소가 있는지 확인한다**

DNS(Doman Name System)이란?

name server들이 계층적 구조를 이루어 만들어진 분산 DB이며, URL들의 이름과 IP주소를 저장하고 있다.

인터넷에 있는 모든 URL들에는 고유의 IP 주소가 지정되어있다. 이 IP 주소를 통해서 해당 웹사이트를 호스팅하고 있는 서버 컴퓨터에 접근을 할 수 있다.

DNS의 가장 큰 목적은 사람들에게 편리함을 주기 위해서이다. 웹사이트에 접속하기 위해 IP주소를 치는 것은 불편하기 때문에 도메인 주소를 이용하는데, 도메인 주소와 맞는 IP주소를 매핑시켜주는 역할을 DNS가 한다.

이처럼 DNS는 전화번호부와 비슷한 역할을 한다, 웹사이트의 이름들과 웹사이트를 접근하기 위해 필요한 IP주소를 저장하고 있다.

<img src="https://aerial-cap-9df.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F91c83630-ec38-4543-9744-04bd64e87241%2FKakaoTalk_20220915_205359715.jpg?table=block&id=2a71e234-b8eb-48ce-a323-9fd0e9ab438c&spaceId=54a976d5-bf03-458e-acc7-499adb0c8680&width=2000&userId=&cache=v2" width="800" height="800">
<img src="https://aerial-cap-9df.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F20f0692c-11d5-434b-9c7e-611176764af0%2FKakaoTalk_20220915_205118939.jpg?table=block&id=5f294645-65ad-4f84-af3d-a9d87334c2aa&spaceId=54a976d5-bf03-458e-acc7-499adb0c8680&width=2000&userId=&cache=v2" width="800" height="800">

호스트가 DNS 쿼리를 던지면 제일 먼저 도달하는 곳이 Local DNS서버이다.

DNS는 3가지의 서버 ( 순서대로 root DNS server, top-level domain(TLD) DNS servers, authoritative DNS servers)로 이루어져 있다.

top-level domain(TLD) DNS servers는 도메인 끝 자리 .com, .org, .edu, .kr, .uk 등에 따라서 나뉜다.

authoritative servers가 진짜 IP주소를 리턴한다.

웹사이트 이름을 브라우저에 검색하면 브라우저는 DNS 기록을 4가지의 캐시에서 확인을 한다

1. 가장 먼저 브라우저 캐시를 확인한다. 브라우저는 일정기간 동안(유저가 이전에 설정한)의 DNS 기록들을 저장하고 있다. DNS query가 이 곳에서 가장 먼저 실행이 된다.
2. 그 다음에 브라우저는 OS 캐시를 확인한다. 브라우저 캐시에 웹사이트 이름의 IP 주소가 발견되지 않았다면, 브라우저는 systemcall을 통해서 OS가 저장하고 있는 DNS 기록들의 캐시에 접근한다
3. 그 다음에는 router 캐시를 확인한다. 컴퓨터에 DNS 기록을 찾지 못하면 브라우저는 DNS 기록을 캐싱하고 있는 router와 통신을 해서 찾으려고 한다.
4. 그래도 못 찾는다면 마지막으로, ISP 캐시를 확인한다. ISP는 DNS 서버를 구축하고 있고 브라우저가 마지막으로 DNS 기록이 있기를 바라며 접근하게 된다.

## **3. 요청한 URL이 캐시에 없으면, ISP의 DNS 서버가 www.google.com을 호스팅하고 있는 서버의 IP 주소를 찾기 위해 DNS query를 날린다**

www.google.com에 접속하고 싶으면 IP 주소를 반드시 알아야 한다. DNS query의 목적은 여러 다른 DNS 서버들을 검색해서 해당 사이트의 IP 주소를 찾는 것이다. 이러한 검색을 `recursive search`라고 부른다. IP 주소를 찾을 때 까지 DNS 서버에서 다른 DNS 서버를 오가면서 반복적으로 검색하던지 못 찾아서 에러가 발생할 때 까지 검색을 진행한다.

이 상황에서, ISP의 DNS 서버를 DNS recursor라고 부르고 인터넷을 통해 다른 DNS 서버들에게 물어 물어 도메인 이름의 올바른 IP 주소를 찾는데 책임을 갖고 있다. 다른 DNS 서버들은 name server라고 불린다. 이들은 웹사이트 도메인 이름의 구조에 기반해서 검색을 하기때문이다.

도메인 이름 구조에 기반해서 검색한다고 하면 이해하기 어려워보이지만 원리는 매우 간단하다. 일단 도메인 이름들의 구조를 보면 다음과 같다

![https://devjin-blog.com/static/df40acaf929fb371a270155e2ef49a36/fcda8/browser_work_dns_2.png](https://devjin-blog.com/static/df40acaf929fb371a270155e2ef49a36/fcda8/browser_work_dns_2.png)

우리가 마주하는 웹사이트 URL들은 **third-level domain, second-level domain, top-level domain**을 가지고 있다. 각 레벨별로 자신들만의 name 서버가 있고 여기서 DNS look up 프로세스 중에 쿼리가 진행된다.

**www.[google.com](http://google.com/)에 대해서, 처음에 DNS recursor가 root name server에 연락을 한다. root name 서버는 `.com` 도메인 name server로 리다이렉트한다. `.com` name server는 `google.com` name server로 라디아렉트한다. `google.com` name server는 DNS 기록에서 www.google.com에 매칭되는 IP 주소를 찾고 DNS recursor로 보내게 된다.**

이 모든 요청들은 작은 데이터 패킷들을 통해서 보내진다. 패킷 안에는 보내는 요청의 내용과 DNS recursor의 IP 주소가 포함되어 있다. 이 패킷들은 원하는 DNS 기록을 가진 DNS 서버에 도달할 때 까지 클라이언트와 서버를 여러번 오간다. 패킷들이 움직이는 것도 routing table에 기반한다. Routing table을 통해서 어떤 길로 가야 가장 빠른지 확인할 수 있다. 만약 패킷이 도중에 loss되면 request fail error가 발생하게 된다.

## **4. Browser가 서버와 TCP connection을 한다**

브라우저가 올바른 IP 주소를 받게 되면 서버와 connection을 빌드하게 된다. 브라우저는 인터넷 프로토콜을 사용해서 서버와 연결이 된다. 인터넷 프로토콜의 종류는 여러가지가 있지만, 웹사이트의 **HTTP 요청의 경우에는 일반적으로 TCP를 사용한다.**

클라이언트와 서버간 데이터 패킷들이 오가려면 TCP connection이 되어야 한다. **TCP/IP three-way handshake**라는 프로세스를 통해서 클라이언트와 서버간 connection이 이뤄지게 된다. 단어 그대로 클라이언트와 서버가 SYN과 ACK메세지들을 가지고 3번의 프로세스를 거친 후에 연결이 된다.

1. 클라이언트 머신이 SYN 패킷을 서버에 보내고 connection을 열어달라고 물어본다
2. 서버가 새로운 connection을 시작할 수 있는 포트가 있다면 SYN/ACK 패킷으로 대답을 한다
3. 클라이언트는 SYN/ACK 패킷을 서버로부터 받으면 서버에게 ACK 패킷을 보낸다

이 과정이 끝나면 TCP connection이 완성되는 것이다.

## **5. Browser가 웹 서버에 HTTP 요청을 한다.**

TCP로 연결이 되었다면, 데이터를 전송하면 된다.

클라이언트의 브라우저는 GET 요청을 통해 서버에게 www[.google.com](http://maps.google.com/) 웹페이지를 요구한다. 요청을 할 때 비밀 자료들을 포함하던지, form을 제출하는 상황에서는 POST 요청을 사용할 수도 있다. 이 요청을 할 때 다른 부가적인 정보들도 함께 전달이 된다:

- browser identification(User-Agent 헤더)
- 받아들일 요청의 종류(Accept 헤더)
- 추갖거인 요청을 위해 TCP connection을 유지를 요청하는 connection 헤더
- 브라우저에서 얻은 쿠키 정보
- 기타 등등

밑에는 샘플 GET 요청이다 (노란색으로 하이라이트 된 부분이 헤더이다)

![https://devjin-blog.com/static/5bb3652abc4ebf86df5921c7f54922b0/fcda8/browser_work_get_3.png](https://devjin-blog.com/static/5bb3652abc4ebf86df5921c7f54922b0/fcda8/browser_work_get_3.png)

(HTTP 요청의 내용을 보고 싶으면 Firebug같은 툴을 사용해서 볼 수 있다)

## **6. 서버가 요청을 처리하고 response를 생성한다**

서버는 웹서버를 가지고 있다(i.e. Apache, IIS...). 이들은 브라우저로부터 요청을 받고 request handler한테 요청을 전달해서 요청을 읽고 response를 생성하게 한다. Request handler란 ASP.NET, PHP, Ruby 등으로 작성된 프로그램을 의미한다. 이 request handler는 요청과 요청의 헤더, 쿠키를 읽어서 요청이 무엇인지 파악하고 필요하다면 서버에 정보를 업데이트 한다. 그 다음에 response를 특정한 포맷으로(JSON, XML, HTML) 작성한다.

## **7. 서버가 HTTP response를 보낸다**

서버의 response에는 요청한 웹페이지, status code, compression type(Content-Encoding) - 어떻게 인코딩 되어 있는지, 어떻게 페이지를 캐싱할지(Cache-Control), 설정할 쿠키가 있다면 쿠키, 개인정보 등이 포함된다.

샘플 HTTP 서버 response는 다음과 같다

![https://devjin-blog.com/static/9d78801ad76a05e7b22cef1a428a494b/fcda8/browser_work_response_4.png](https://devjin-blog.com/static/9d78801ad76a05e7b22cef1a428a494b/fcda8/browser_work_response_4.png)

위 response의 첫줄은 status code를 나타낸다. Status code란 현재 response의 상태를 의미하고 총 5가지의 종류가 있다:

- 1xx은 정보만 담긴 메세지라는 것을 의미한다
- 2xx response가 성공적이라는 것을 의미한다
- 3xx 클라이언트를 다른 URL로 리다이렉트함을 의미한다
- 4xx 클라이언트 측에서 에러가 발생했음을 의미한다
- 5xx 서버 측에서 에러가 발생했음읠 의미한다

## **8. Browser가 HTML content를 보여준다**

브라우저는 HTML content를 단계적으로 보여준다. 처음에는 HTML의 스켈레톤(기본 틀이라고 보면 될듯하다)을 렌더링한다. 그 다음에는는 HTML tag들을 체크하고 나서 추가적으로 필요한 웹페이지 요소들을(이미지, CSS 스타일시트, Javascript 파일, 등) GET으로 요청한다. 이 정적인 파일들은 브라우저에 의해 캐싱이 되서 나중에 해당 페이지를 방문할 때 다시 서버로부터 불러와지지 않도록 한다. 그 다음에는 그토록 원했던 www.google.com의 모습이 보이게 된다.

www.google.com을 검색하고 웹페이지가 뜰 때까지 엄청 많은 일들이 일어나지만, 이 모든 일들이 1초도 되지 않아서 완료가 된다.

---

문제

1. DNS서버를 크게 나누면 몇 가지로 분류할 수 있으며, 접속하려는 웹사이트의 진짜 ip를 리턴하는 서버는?
2. 웹사이트 http요청을 통해 서버와 통신하려할 때 사용되는 프로토콜은?
