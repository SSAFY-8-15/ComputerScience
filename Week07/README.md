
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

# Java Backend 대비 퀴즈 (💧 & 🔥)

### 1. [MVC Architecture] 대부분의 상용화된 웹 백엔드 프레임워크는 아키텍쳐로 MVC패턴을 사용한다. MVC 패턴에서 M,V,C가 의미하는 바를 쓰시오. 💧
```
M :

V :

C :
```
### 2. [Java Servlet] 어떤 사용자가, Request를 날려, MyHttpServlet내 doGet메소드가 총 3회 호출되었을 경우, Servlet 인터페이스내 메소드 init(), service(), destroy() 메소드의 호출 횟수로 적절한 것은? 💧
```
(1) init() 1회, service() 1회, destroy() 1회

(2) init() 3회, service() 1회, destroy() 1회

(3) init() 1회, service() 3회, destory() 1회

(4) init() 3회, service() 3회, destroy() 3회
```
### 3. 다음 중 올바르지 못한 Servlet url-pattern은? 🔥
```
(1) @WebServlet("*.do”)

(2) @WebServlet("/ssafy", "/ssafy2")

(3) @WebServlet("/ssafy/*/ssafy2”)

(4) @WebServlet({”/ssafy”})
```
### 4. HTTP Request Method중 Get방식과 Post 방식의 차이점 하나만 쓰시오. 💧
```



```
### 5. JSP의 기본객체 영역 Scope 4가지에 대한 설명으로 옳은 것은? 🔥
```
(1) pageContext의 scope는 page내에서 유효하므로, jsp:include 를 통해 다른 페이지에 접근했을때의 pageContext는 기존의 것과 다른 새로운 객체를 가리키게 된다.

(2) session scope는 한번 생성되면, application이 종료되기 전까지 사라지지 않는다.

(3) 모든 기본객체의 scope는 el 태그내 생략이 가능하며, el 태그로 내장 객체 접근시pageContext→request→session→application 순으로 검색하며, 검색 되지 않았을 경우 예외를 내놓지 않고 null이 출력된다.

(4) pageConext는 서블릿에서 request.getServletContext()를 통해 접근 할 수 있으며, 해당 객체의 속성을 추가했을 경우 해당 객체를 jsp에 전달하기 위해서는 오로지 forward만 가능하다.
```
### 6. Web Server와 Web Application Server의 동작으로 잘못된 것은? 🔥
```
(1) Web Server는 http request를 식별하고 통합자원식별자(URI)를 통해 적절한 resource에 대한 조회, 삽입, 수정, 삭제를 수행 할 수 있다.

(2) Web Server는 식별된 URI에 해당하는 자원을 찾을 수 없는 경우 reponse내 http status에 404 Not Found를 넣어 보낸다.

(3) Web Application Server는 사용자 요청에 따라 적절한 response를 가공하여 내보낼 수 있다.

(4) Web Application Server는 사용자의 요청에 따른 상태를 session, application등의 형태로 기록 및 보관할 수 있으며, 해당 데이터에 대한 무결성 및 영속성을 보장한다.
```
### 7. 다음 EL expression이 True가 되기 위한 조건으로 옳지 않은 것은?💧
```
${empty requestScope[”ssafy”].val}
```
```
(1) [ssafy.](http://ssafy.name)val == null

(2) [ssafy.](http://ssafy.name)val 이 String이고, ssafy.val == “”

(3) ssafy.val 이 Collection이고, ssafy.val.isEmpty() == true

(4) ssafy.val 이 배열이고, ssafy.val[0] == ssafy.val[1] .. == ssafy.val[length-1] == null
```
### 8. 자바 EE에서는 서버단에서 페이지를 동적으로 생성하기 위한 기술로 JSP를 사용하며, JSP내 자바 코드를 사용하지 않고 로직을 내장하는 효율적인 방법으로 JSTL을 도입한바 있다. 이때, JSP와 JSTL은 무엇의 약자일까?💧
```
JSP :

JSTL:
```
### 9. Session과 Cookie에 대한 설명으로 옳지 않은 것은? 🔥
```
(1) Session은 서버에서만 접근 가능한 객체이며, 서블릿에서 request.getSession()을 통해 접근 할 수 있다.

(2) 서버 개발자는 request.getSession()을 통해 얻은 세션의 소유자를 구분하기 위해 attribute내 유저를 구분 할 수 있는 구분자(key)를 추가하여 사용해야 한다.

(3) Cookie는 클라이언트내 파일의 형태로 저장되며, 특정 쿠키는 request을 보낼 때 header에 포함되어 서버로 전송된다.

(4) Cookie는 유효기간, 도메인, 경로, 이름, 값을 가지며, 이름은 Cookie를 구별하는데 사용한다.
```
### 10. 다음은 JSP파일의 일부이다. 해당 부분을 JSTL/EL 문법을 통해 고친것으로 옳은 것은? 🔥
```
<%

for(Article article : articles){

%><td><%=article.getUserName()%></td><%

}

%>
```
```
(1)

<c:forEach var="article" items="${articles}">

<td>${article.userName}</td>

</c:forEach>

(2)

<c:forEach var="article" items="articles">

<td>${article.userName}</td>

</c:forEach>

(3)

<c:forEach var=article items=${articles}>

<td>${article.userName}</td>

</c:forEach>

(4)

<c:forEach var="${article}" items=”${articles}”>

<td>${article.userName}</td>

</c:forEach>
```
### 11. 다음은 MVC Model2의 구조의 일부를 나타낸 것이다. 다음 그림을 보고 잘못된 해석을 한 학생을 고르시오? 💧

![Untitled](https://github.com/SSAFY-8-15/ComputerScience/blob/main/Week07/mvc_model2.png?raw=true)
```
(1) 김철수 : Java EE에서의 MVC Model2에서는 View단을 JSP로, Controller단을 Servlet으로 구현하고 있어.

(2) 서민권 : **(A)**는 Servlet에 의해 메소드가 호출되고 있어, 직접 데이터베이스에 접근하고 있지도 않아. **(A)**는 서버에 핵심이 되는 비즈니스 로직이 담겨있는 것 같아. (A)는 틀림없이 Service일 것 같아.

(3) 임한경 : **(B)**는 데이터베이스를 사용해 데이터를 조회하거나 조작하는 역할을 가지고 있군. **(B)**는 DTO(Data Transfer Object)에 해당하는 것 같아.

(4) 최승결 : **(C)**는 특정한 기능을 수행하는 로직이라기 보다, 순수한 데이터 객체에 해당하는 것 같아. (C)는 VO( Value Object )라고 볼 수 있어.
```
### 12. JSP 태그 문법으로 옳지 않은 것은? 💧
```
(1) Script <% %>

(2) Declaration <%! %>

(3) Expression <%= %>

(4) Comment <%@ %>
```
### 13. JavaBeans에 대한 설명으로 옳은 것은? 🔥
```
(1) JavaBeans는 자바로 작성된 소프트웨어 컴포넌트이며, EJB (Enterprise JavaBeans) 라고도 한다.

JavaBeans는 일종의 컨벤션(규약)이기 때문에, 하나이상의 어노테이션 혹은 어떠한 클레스도 상속하지 않아도 된다.


(2) JavaBeans는 하나 이상의 데이터를 파라미터로 받는 생성자를 반드시 포함해야 한다. 또한 직렬화를 하기 위해 반드시 부모 클레스중 하나는 Serializable을 구현해야 한다.


(3) JavaBeans는 필드변수를 private로 지정하며, jsp내에서 접근하기 위해 getter setter를 반드시 명시적으로 구성해야 한다.

get, set은 엄격한 네이밍 컨벤션(get + variable name with Capital Letter)를 지켜야 하며, obj.getName()과 같은 경우 EL에서 ${[obj.name](http://obj.name)}을 통해 호출 할 수 있다.


(4) jsp내 action tag를 통해 javabean 객체를 생성하거나, 값을 수정 및 조회할 수 있다.

javabean객체를 생성하기 위해 <jsp:userBean id=”objName” class=”com.ssafy.MyClass”/> 을 사용하며

값을 조회 또는 수정하기 위해 jsp:setAttribute jsp:getAttribute 를 사용하며, 각각 정의된 getXXX() 및 setXXX() 메소드가 호출된다.

해당 명령어를 사용하기 위해서는 jstl 라이브러리 및 jstl 라이브러리를 사용하기 위한 선언문을 미리 정의해야 한다.
```
### 14. HttpServletRequest request와 HttpServletResponse response의 내장함수중 아무거나 골라 각각 3개씩 쓰시오. 💧
```



```

### 15. 다음은 Servlet에서의 페이지 이동 (Redirect, Forward)에 대한 설명이다. 옳지 않은 것은? 💧
```
(1) 리다이렉션을 통해 페이지를 전환했을 경우. 해당 서블릿에서 정의된 request내 attribute 및 parameter은 사라지게 된다.

(2) 리다이렉션은 response.sendRedirect(path); 를 이용한다.

(3) 포워드를 통해 특정 jsp 파일로의 페이지를 전환했을 경우. jsp 페이지 내에서 기존 서블릿에서 정의된 request내 attribute를 이용할 수 있다.

(4) 포워드는

ResponseDispatcher rd = response.getResponseDispatcher(path);

rd.forward(request,response);

를 이용한다.
```
### 16. MVC Model1과 MVC Model2와의 차이점을 한 가지만 쓰시오. 💧
```



```
-   정답

### 1. [MVC Architecture] 대부분의 상용화된 웹 백엔드 프레임워크는 아키텍쳐로 MVC패턴을 사용한다. MVC 패턴에서 M,V,C가 의미하는 바를 쓰시오. 💧

M : **Model**

V : **View**

C : **Controller**

### 2. [Java Servlet] 어떤 사용자가, Request를 날려, MyHttpServlet내 doGet메소드가 총 3회 호출되었을 경우, Servlet 인터페이스내 메소드 init(), service(), destroy() 메소드의 호출회수로 적절한 것은? 💧

(1) init() 1회, service() 1회, destroy() 1회

(2) init() 3회, service() 1회, destroy() 1회

**(3) init() 1회, service() 3회, destory() 1회**

(4) init() 3회, service() 3회, destroy() 3회

### 3. 다음중 올바르지 못한 Servlet url-pattern은? 🔥

(1) @WebServlet("*.do”)

**(2) @WebServlet("/ssafy", "/ssafy2") ⇒ @WebServlet({"/ssafy", "/ssafy2"})**

(3) @WebServlet("/ssafy/*/ssafy2”)

(4) @WebServlet({”/ssafy”})

### 4. HTTP Request Method중 Get방식과 Post 방식의 차이점 하나만 쓰시오. 💧

**Get방식은 헤더에 파라미터가 노출되지만, Post방식은 노출되지 않는다.**

**Get방식은 파라미터의 길이 제한이 있지만, Post방식은 길이제한이 없다.**

**….**

### 5. JSP의 기본객체 영역 Scope 4가지에 대한 설명으로 옳은 것은? 🔥

**(1) pageContext의 scope는 page내에서 유효하므로, jsp:include 를 통해 다른 페이지에 접근했을때의 pageContext는 기존의 것과 다른 새로운 객체를 가리키게 된다.**

(2) session scope는 한번 생성되면, application이 종료되기 전까지 사라지지 않는다.

⇒ 갱신하지 않으면 session scope는 정해진 수명을 다하면 사라진다.

(3) 모든 기본객체의 scope는 el 태그내 생략이 가능하며, el 태그를 통해 내장 객체 접근시pageContext→request→session→application 순으로 검색하며, 검색 되지 않았을 경우 예외를 내놓지 않고 null이 출력된다.

⇒ null이 출력되는 대신에 공백 문자열 “”이 출력된다.

(4) pageConext는 서블릿에서 request.getServletContext()를 통해 접근 할 수 있으며, 해당 객체의 속성을 추가했을 경우 해당 객체를 jsp에 전달하기 위해서는 오로지 forward만 가능하다.

⇒ request.getServletContext()는 application scope에 접근하는데 쓰인다. 또한 forward 여부와 관계없이 pageContext는 jsp Page단에서 생성되고 소멸된다.

### 6. Web Server와 Web Application Server의 동작으로 잘못된 것은? 🔥

(1) Web Server는 http request를 식별하고 통합자원식별자(URI)를 통해 적절한 resource에 대한 조회, 삽입, 수정, 삭제를 수행 할 수 있다.

(2) Web Server는 식별된 URI에 해당하는 자원을 찾을 수 없는 경우 reponse내 http status에 404 Not Found를 넣어 보낸다.

(3) Web Application Server는 사용자 요청에 따라 적절한 response를 가공하여 내보낼 수 있다.

**(4) Web Application Server는 사용자의 요청에 따른 상태를 session, application등의 형태로 기록 및 보관할 수 있으며, 해당 데이터에 대한 무결성 및 영속성을 보장한다.**

⇒ 영속성은 보장하지 않는다. Database에 대한 내용이다.

### 7. 다음 EL expression이 True가 되기 위한 조건으로 옳지 않은 것은?💧

${empty requestScope[”ssafy”].val}

(1) [ssafy.](http://ssafy.name)val == null

(2) [ssafy.](http://ssafy.name)val 이 String이고, ssafy.val == “”

(3) ssafy.val 이 Collection이고, ssafy.val.isEmpty() == true

**(4) ssafy.val 이 배열이고, ssafy.val[0] == ssafy.val[1] .. == ssafy.val[length-1] == null**

⇒ 해당 결과는 true가 나온다.

### 8. 자바 EE에서는 서버단에서 페이지를 동적으로 생성하기 위한 기술로 JSP를 사용하며, JSP내 자바 코드를 사용하지 않고 로직을 내장하는 효율적인 방법으로 JSTL을 도입한바 있다. 이때, JSP와 JSTL은 무엇의 약자일까?💧

JSP : **Java Server Page**

JSTL: **JSP Standard Tag Library**

### 9. Session과 Cookie에 대한 설명으로 옳지 않은 것은? 🔥

(1) Session은 서버에서만 접근 가능한 객체이며, 서블릿에서 request.getSession()을 통해 접근 할 수 있다.

**(2) 서버 개발자는 request.getSession()을 통해 얻은 세션의 소유자를 구분하기 위해 attribute내 유저를 구분 할 수 있는 구분자(key)를 추가하여 사용해야 한다.**

⇒ getSession()을 했을 시, 이미 식별된 session을 받는다. JSESSIONID는 이미 기본적으로 세션내 Key로 포함된다.

(3) Cookie는 클라이언트내 파일의 형태로 저장되며, 특정 쿠키는 request을 보낼 때 header에 포함되어 서버로 전송된다.

(4) Cookie는 유효기간, 도메인, 경로, 이름, 값을 가지며, 이름은 Cookie를 구별하는데 사용한다.

### 10. 다음은 JSP파일의 일부이다. 해당 부분을 JSTL/EL 문법을 통해 고친것으로 옳은 것은? 🔥

<%

for(Article article : articles){

%><td><%=article.getUserName()%></td><%

}

%>

**(1)**

**<c:forEach var="article" items="${articles}">**

**<td>${article.userName}</td>**

**</c:forEach>**

(2)

<c:forEach var="article" items="articles">

<td>${article.userName}</td>

</c:forEach>

(3)

<c:forEach var=article items=${articles}>

<td>${article.userName}</td>

</c:forEach>

(4)

<c:forEach var="${article}" items=”${articles}”>

<td>${article.userName}</td>

</c:forEach>

### 11. 다음은 MVC Model2의 구조의 일부를 나타낸 것이다. 다음 그림을 보고 잘못된 해석을 한 학생을 고르시오? 💧

![Untitled](https://github.com/SSAFY-8-15/ComputerScience/blob/main/Week07/mvc_model2.png?raw=true)

(1) 김철수 : Java EE에서의 MVC Model2에서는 View단을 JSP로, Controller단을 Servlet으로 구현하고 있어.

(2) 서민권 : **(A)**는 Servlet에 의해 메소드가 호출되고 있어, 직접 데이터베이스에 접근하고 있지도 않아. **(A)**는 서버에 핵심이 되는 비즈니스 로직이 담겨있는 것 같아. (A)는 틀림없이 Service일 것 같아.

**(3) 임한경 : (B)는 데이터베이스를 사용해 데이터를 조회하거나 조작하는 역할을 가지고 있군. (B)는 DTO(Data Transfer Object)에 해당하는 것 같아.**

⇒ DAO(Data Access Object)가 맞는 말이다.

(4) 최승결 : **(C)**는 특정한 기능을 수행하는 로직이라기 보다, 순수한 데이터 객체에 해당하는 것 같아. (C)는 VO( Value Object )라고 볼 수 있어.

### 12. JSP 태그 문법으로 옳지 않은 것은? 💧

(1) Script <% %>

(2) Declaration <%! %>

(3) Expression <%= %>

**(4) Comment <%@ %>**

⇒ Comment는 <%— —%>로 쓴다

### 13. JavaBeans에 대한 설명으로 옳은 것은? 🔥

(1) JavaBeans는 자바로 작성된 소프트웨어 컴포넌트이며, EJB (Enterprise JavaBeans) 라고도 한다.

JavaBeans는 일종의 컨벤션(규약)이기 때문에, 하나이상의 어노테이션 혹은 어떠한 클레스도 상속하지 않아도 된다.

⇒ EJB는 JavaBeans와 관계가 없다.

(2) JavaBeans는 하나 이상의 데이터를 파라미터로 받는 생성자를 반드시 포함해야 한다. 또한 직렬화를 하기 위해 반드시 부모 클레스중 하나는 Serializable을 구현해야 한다.

⇒ 기본 생성자만 포함하면 된다.

**(3) JavaBeans는 필드변수를 private로 지정하며, jsp내에서 접근하기 위해 getter setter를 반드시 명시적으로 구성해야 한다.**

**get, set은 엄격한 네이밍 컨벤션(get + variable name with Capital Letter)를 지켜야 하며, obj.getName()과 같은 경우 EL에서 ${[obj.name](http://obj.name)}을 통해 호출 할 수 있다.**

(4) jsp내 action tag를 통해 javabean 객체를 생성하거나, 값을 수정 및 조회할 수 있다.

javabean객체를 생성하기 위해 <jsp:userBean id=”objName” class=”com.ssafy.MyClass”/> 을 사용하며

값을 조회 또는 수정하기 위해 jsp:setAttribute jsp:getAttribute 를 사용하며, 각각 정의된 getXXX() 및 setXXX() 메소드가 호출된다.

해당 명령어를 사용하기 위해서는 jstl 라이브러리 및 jstl 라이브러리를 사용하기 위한 선언문을 미리 정의해야 한다.

⇒ setAttribute, getAttribute는 없다. 대신 setProperty, getProperty를 쓴다. jsp 액션 태그는 jstl문법과 무관하므로, jstl라이브러리 선언 역시 필요없다.

### 14. HttpServletRequest request와 HttpServletResponse response의 내장함수중 아무거나 골라 각각 3개씩 쓰시오. 💧

**request.getSession(), request.getAttribute(), request.getHeader(), request.getReader(), request.getContextPath(), request.setCharacterEncoding() ….**

**response.addCookie(), response.sendRedirect(), response.sendError(), response.setContentType(), response.getWriter(), response.addHeader(), ….**

### 15. 다음은 Servlet에서의 페이지 이동 (Redirect, Forward)에 대한 설명이다. 옳지 않은 것은? 💧

(1) 리다이렉션을 통해 페이지를 전환했을 경우. 해당 서블릿에서 정의된 request내 attribute 및 parameter은 사라지게 된다.

(2) 리다이렉션은 response.sendRedirect(path); 를 이용한다.

(3) 포워드를 통해 특정 jsp 파일로의 페이지를 전환했을 경우. jsp 페이지 내에서 기존 서블릿에서 정의된 request내 attribute를 이용할 수 있다.

**(4) 포워드는**

**ResponseDispatcher rd = response.getResponseDispatcher(path);**

**rd.forward(request,response);**

**를 이용한다.**

⇒ RequestDispatcher가 올바른 답안이다.

### 16. MVC Model1과 MVC Model2와의 차이점을 한가지만 쓰시오. 💧

**MVC Model1은 View와 Controller의 구분이 없으나, MVC Model2는 구분한다.**

**JAVA EE에서의 MVC Model1은 JSP 페이지 내에서 비즈니스 로직이 포함된 Service객체내 메소드를 직접 호출하여 사용한다. 그러나 MVC Model2에서는 Service객체내 메소드는 반드시 Servlet에서만 호출 할 수 있다.**

**MVC Model1은 개발속도가 빠른 대신, 유지보수가 어렵고, MVC Model2는 개발속도가 상대적으로 느리나, 유지보수가 쉽다.**
	
