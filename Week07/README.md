
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


