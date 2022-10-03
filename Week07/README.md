
1. URL 구조를 나타낸 것이다. 다음 빈칸을 채우시오
  ![image](https://user-images.githubusercontent.com/79408217/193569884-4eb4e7c6-0650-415d-bb79-f6ad950c82a9.png)
    ```
    1.
    2.
    3.
    ```
 2. JSP 스크립팅 요소와 그 형식의 예가 옳바르게 연결되지 않은 것은?
```
    1.선언 (Declaration) 
        
        ```html
        <%! String name; %>
        ```
        
    2.스크립틀릿 (scriptlet) 
        
        ```html
        <%
        List<Board> boards = new ArrayList<>();
        Object obj = request.getAttribute("boards");
        if(obj != null){
        boards = (List<Board>)obj;
        }
        %>
        ```
        
    3.스크립틀릿 (scriptlet)
        
        ```html
        *<%
        	int cnt = 1;
        	for(Board b: boards ){
        		%>
        			<tr>
        					<td><%=cnt++ %></td>
        					<td><%=b.getUser_id()%></td>
        					<td><a href='./boards?command=detail&article_no=<%=b.getArticle_no()%>'><%= b.getSubject() %></a></td>
        					<td><%=b.getRegister_time()%></td>
        					<td><a href='./boards?command=delete&article_no=<%=b.getArticle_no()%>'>삭제</a></td>
        			</tr>
        		<% 
        	}
        %>*
        ```
        
    4.표현식 (Expression)
        ```html
        <a href='<%=request.getAttribute("url")%>'><%=request.getAttribute("title"); %></a>
        ```
        
         
        
    5.주석 (Comment)
        ```html
        <%-- JSP주석 --%>
        ```
```
 3. JSP와 HTML 주석의 차이점은?

```
	



```
 4. JSP 기본 객체들에 대한 설명으로 틀린 것을 고르시오
```
    1. request: HTML 폼 요소의 선택 값 등 사용자 입력정보를 읽어 올 때 사용
    2. response: 사용자 요청에 대한 응답을 처리하기 위해 사용
    3. PageContext: 웹 서버의 애플리케이션 처리와 관련된 정보를 참조하기 위해 사용
    4. session: 클라이언트에 대한 세션 정보를 처리하기 위해 사용
```
5. 기본객체들의 영역(Scope)에 대한 설명이다. 각 영역에 해당하는 기본객체를 쓰시오
```
    1. 하나의 jsp페이지를 처리할 때 사용되는 영역. 한번의 클라이언트 요청에 대하여 하나의 JSP 페이지가 호출되며, 이때 단 한 개의 page객체만 대응된다. 
    페이지 영역에 저장한 값은 페이지를 벗어나면 사라진다.
    
    2. 하나의 HTTP 요청을 처리할 때 사용되는 영역
    웹 브라우저가 요청을 할 때마다 새로운 request객체가 생성됨
    request영역에 저장한 속성은 그 요청에 대한 응답이 완료되면 사라진다.
    
    3. 하나의 웹브라우저와 관련된 영역.
    같은 웹 브라우저 내에서 요청되는 페이지들은 같은 session들을 공유하게 됨.
    *로그인 정보를 저장한다 
```
 ### 답
 ```
 1. url, parameter Name, parameter Value

 2. 답 4번 표현식에서 문자열 뒤에 ; 붙이면 안 됨

 3. 데이터가 클라이언트로 넘어갈 때 HTML 주석은 같이 넘어가지만 jsp 주석은 자바라서 넘어가지 않는다

 4. 3번은 application 객체에 대한 설명

 5. a: pageContext
	b: request
	c: session
```


문제

1.  Web Server + Application Server = ?
2.  백엔드에서 서버와 데이터베이스 간에 DB데이터 공유를 할 수 있게 해주는 것은?
3.  JSP와 Servlet의 차이점?
4.  사용자 정의 Servlet 인 MyServlet이 있을 때, MyServlet의 상속 구조를 순서대로 나열한 것은?
```
1.  MyServlet —(extends)→ HttpServlet —(extends)→ GenericServlet —(extends)→ Servlet
    
2.  MyServlet —(extends)→ HttpServlet —(extends)→ GenericServlet —(Implements)→ Servlet
    
3.  MyServlet —(extends)→ GenericServlet —(extends)→ HttpServlet —(extends)→ Servlet
    
4.  MyServlet —(extends)→ GenericServlet —(extends)→ HttpServlet —(Implements)→ Servlet
```

5.  Servlet LifeCycle의 요소 3가지를 순서대로 말하고, 서블릿 호출시 몇 번씩 불리는지 각각 적으세요
```




```
6.  세션의 용량 제한은 없다. 그렇다면 쿠키의 용량 제한은?
```
1.  제한 없음
    
2.  클라이언트에 총 300개 쿠키 저장, 도메인당 10개, 1쿠키당 2kb
    
3.  클라이언트에 총 300개 쿠키 저장, 도메인당 20개, 1쿠키당 4kb
    
4.  클라이언트에 총 300개 쿠키 저장, 도메인당 40개, 1쿠키당 8kb
```

7.  JSP의 기본 객체 4가지를 쓰세요
8.  세션과 쿠키의 저장 형식은?type
9.  EL 표현방식 중 Dot로 표현한것을 [ ]로 표현해보세요
```
${[userinfo.name](http://userinfo.name)} = ${userinfo[”name”]}
```
10.  JSTL에서 core 라이브러리를 사용하려고 한다. 다음 밑줄에 들어갈 단어는?
```
<%@_____ prefix="___" uri="[http://java.sun.어쩌구/core](http://java.sun.xn--2e0bl47b2hd/core)" %>
```

답

1.  ```WAS```
2.  ```JDBC```
3. ``` JSP는 HTML안에 자바코드가, Servlet은 자바코드 안에 HTML이 있다.```
4.  
```
2번 MyServlet —(extends)→ HttpServlet —(extends)→ GenericServlet —(Implements)→ (interface)Servlet
```
5.
```
-init() ← 1번

-service() ← 부를 때마다

-destroy() ← 1번
```
6.  ```3번  클라이언트에 총 300개 쿠키 저장, 도메인당 20개, 1쿠키당 4kb```
7.  ```pageContext, request, session, application```
8.  ```세션: Object, 쿠키:String```
9.  ```${userinfo[”name”]}```
10.  ```taglib , c```


# 시험대비 문제

**Q . 다음중 틀린거 모두 고르시오**
```
1.  <%= 문자열 %>
2.  <% out.print(문자열); %>
3.  <%= 문자열; %>
4.  <% out.print(문자열) %>
```
답: ```3,4 <%= 문자열 %> == <% out.print(문자열); %>```

**Q . jsp 구성요소 3가지:**
```




```

답:
```
1.  디렉티브 - @page : import, content, encoding, session @taglib : jstl @include : 정적문서포함 file = “포함할파일”
    
2.  스크립트 <% %> 자바코드
    
    <%=%> expression - String만드는거
    
    <%! %> declaration - 선언 ex. <%! String toMsg(String Msg) {
    
    ```
                                                             return msg ! null?msg:””  } %>
    
    ```
    
3.  Helper View Pattern
    
    액션 jsp : useBean id=”ref” class=”a.b.c.Hello”
    
    jsp : setProperty getProperty ← 액션
    
```
**Q . MVC 파트 : 모델1 모델2 차이점 서술하시오**
```





```


답:
```
모델1: view, logic을 모두 jsp페이지 하나에서 처리. client요청오면 java beans, service class 이용하여 작업처리.

구조단순, 직관적. 개발시간 비교적짧아 개발비용감소

but

출력용 html코드와 로직위한 java코드 섞여있어서 jsp복잡해짐

백엔드 프론트엔드 혼재되어 분업힘듬

규모 커지면 유지보수 힘듬, 확장성나쁨

모델2: client요청처리는 서블릿, 로직처리는 service, dao등에서 처리. jsp는 출력만담당

Model = Service, Dao, java beans : 로직 처리하는 모든것 controller한테 데이터받고 결과를 다시 넘김

View = JSP : 모든 화면처리 담당. 결과출력만함

Controller = Servlet : 로직처리위한 model을 호출. 데이터를 필요에따라 request, session에 저장ㅎ고 redirect or forward 방식으로 jsp이용하여 출력

jsp는 단순해짐. 분업용이, 유지보수쉬움, 확장성굳

but

구조복잡, 개방비용증가
```

**Q . 틀린것은? (1개)**
```
1.  쿠키는 서버에서 사용자의 컴퓨터에 저장하는 정보파일이다
2.  쿠키는 Key/Value로 이루어져있고 Object 형태이다``
3.  목적은 세션관리, 개인화, 트래킹이다
4.  세션의 경우 메모리가 허용하는 용량까지 저장가능하다
5.  브라우저마다 저장되는 쿠키가 다르다
```
답:
```
2번 Object → String이다`
```
**Q . client가 요청 100번함 →**
```
init = (  )번호출, destroy = (  )번호출, service = (  )번호출
```

답 : ```init = ( 1 )번호출, destroy = ( 1 )번호출, service = ( 100 )번호출```

**Q . EL : empty 연산자에서 true를 return하지 않는 경우는?**
```
1.  빈 collection 객체
2.  빈 Map 객체
3.  값이 0 → 값이 null이면 true
4.  길이가 0인 배열[]
5.  값이 빈 문자열 (””)
```
답: ```3번```
