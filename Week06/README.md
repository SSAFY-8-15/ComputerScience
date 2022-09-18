Fron-End 과목 평가 대비 문제 및 풀이 모음

1. <Form> 태그의 input 타입이 아닌 것은?
    1. file
    2. reset
    3. hidden
    4. click 
    5. image
    
    정답 : d
    
2. A 태그에 대한 설명 중 틀린 것은?
    1. target의 속성 중 _blank는 링크 내용이 새창이나 새탭에서 열린다.
    2. target의 속성 중 _self는 링크가 있는 현재 윈도우에서 화면이 열린다.
    3. target을 지정하지 않으면 _self가 기본 값이다.
    4. href 속성은 URL이나 문서의 책갈피가 올 수 있다.
    5. tag를 중첩해서 사용할 수 있다. 
    6. 책갈피는 같은 페이지 안에서 특정요소 클릭시 그 위치로 한 번에 이동시키며 #을 붙인다.
    
    정답 : e
    
3. 다음 중 CSS에 대한 설명으로 틀린 것?
    1. 선택자 (selector) : 규칙이 적용되는 요소
    2. 선언 (declaration) : 선택자에 적용될 스타일로 속성과 값으로 이루어 짐
    3. 속성 (property) : 선택자에서 바꾸고 싶은 요소
    4. 값 (value) : 속성에 적용할 값
    5. 여러 선택자에 동일한 스타일을 적용할 때, semi-colon(;)로 구분하여 나열하며 각 속성은 comma(,)로 구분하여 나열한다. 
    6. 스타일 우선순위는 인라인 스타일 > 내부 스타일 > 외부 스타일 시트 순서이다.
    
    정답:  e, 
    
4. 1번, 2번, 3번, 4번 글자의 색깔을 말하시오
    
    ```
    <style type="text/css">
        div div {color: red;}
        div p {color: green;}
        div > div {color: purple;}
        div > p {color: blue;}
     </style>
     <body>
      <div>1번
        <p>2번</p>
        <div>3번
          <span><div>
            <ul>
              <li><p>4번</p></li>
            </ul>
          </div></span>
        </div>
      </div>
    </body>
    
    ```
    
    정답:  검정, 파랑, 보라, 초록
    
    ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/04daec95-7c6e-4549-969a-223c1b956d26/Untitled.png)
    
5. 다음 결과에 맞게 빈칸을 채우시오
    
    ![https://user-images.githubusercontent.com/79408217/190911954-dcef2d6b-3f28-4f6b-8290-7da4756a2b5a.png](https://user-images.githubusercontent.com/79408217/190911954-dcef2d6b-3f28-4f6b-8290-7da4756a2b5a.png)
    
    ```
        <head>
      <meta charset="UTF-8" />
      <title>Insert title here</title>
      <script type="text/javascript">
        window.onload = function () {
          var color = ['orange', 'cyan', 'purple'];
          var ssafy = document._______________('ssafy');
    
          for (var i = 0; i < ssafy.length; i++) {
            ssafy[i]._____.background = color[i];
          }
        };
      </script>
    </head>
    <body>
      <h2 class="ssafy">Hello SSAFY 3th !!!</h2>
      <h2 class="ssafy">Hello SSAFY 4th !!!</h2>
      <h2 class="ssafy">Hello SSAFY 5th !!!</h2>
    </body>
    
    ```
    
    정답: getElementsByClassName, style
    
6. local 스토리지에 대한 설명으로 틀린 것은 (2개)
    1. 키와 값을 쌍으로 가짐
    2. 도메인과 브라우저별로 저장
    3. 값은 반드시 문자열로 저장
    4. 유효기간이 있어 브라우저를 종료시 데이터가 삭제
    5. 자바스크립트와 java로 동시에 조작
    6. 모바일에서도 사용 가능
        
        
7. 다음 중 block과 inline이 잘못 짝지어진 것은? (3개)
    1. <h1> - block
    2. <p>- inline → block
    3. <div>- block
    4. <a> - inline
    5. <ul>- block
    6. <nav> - inline →block
    7. <span> - inline
    8. <input>- block →inline
    9. <table>-block
    10. <form>-block
    11. <header> - block
    
    정답:   b h f
    
8. JSON 직렬화란 무엇인지 짧게 쓰고, 직렬화에 사용하는 메소드를 적어주세요
    
    정답:  **json→문자열,  .stringify()**
    
9. <div id = “ex”> 예제입니다 </div>에서, ‘예제입니다’ 라는 글자를 JS를 사용해 ‘가나다’로 바꾸고자 할 때 빈칸에 들어갈 단어는?
    
    ```jsx
    document.querySelector("_____***").***__________ = “가나다”;
    ```
    
    정답:  **#ex , innerHTML or innerText**
    
10. 다음 출력 값들을 작성하시오 (JS)
    
    ```jsx
    1. console.log(100/0) = Infinity
    2. console.log(-Infinity / 0) = -Infinity
    3. console.log(0/0) = NaN ←WHY?????????
    4. console.log(parseInt(’1A’)) = 1 ←????????????????쓰레기언어
    5. console.log(”40”**+**5) = 405 문자열
    6. console.log(”40”-5) = 35 숫자
    7. console.log(”1.1”+”1.1”) = 1.11.1
    8. console.log((+”1.1”)+(+”1.1”)) = 2.2
    ```
    
11. 아래와 같은 html을 JS를 사용해 만드려고 한다.
    
    ```
    <body>
    
    <h2>Hello</h2>
    
    </body>
    
    ```
    
    다음 밑줄에 들어갈 말은?
    
    ```jsx
    var title = document.createElement(’h2’);
    
    var msg = document.createTextNode(’Hello’);
    
    title.___________(msg);
    
    document.body.________(title);
    
    ```
    
    정답: 둘 다 **appendChild**
    
12. id값이 third인 부분을 JS를 사용해 지우려고 한다
    
    ```
    <body>
    
    <h2 id=”first”>Hello</h2>
    
    <h2 id=”second”>Hello</h2>
    
    <h2 id=”third”>Hello</h2>
    
    </body>
    
    ```
    

13. 다음 밑줄에 들어갈 말은?

document.body.___**(**);

정답:**removeChild('#third')**

1. 다음 중 false를 반환하는것을 모두 고르시오. false라면 true값이 나오도록 고치시오
    1. "phello-p" |= "hello" : false -> 앞에 p를 빼면됨
    2. "p hello" ~= "hello" : true
    3. 3 !== '3' :true
    4. "helllllllllo" ^= "hel" : true
    5. "p hello-p" ~= "hello" : false -> p hello -p (hello 독립적인 단어로!)
    6. "hellopp" |= "hello" : false -> hello-pp
        
        
        =====해설=====
        |= @@@- 로 시작해야함("-" 필수!)
        |= "hello"  : hello- 로 시작해야함
        phello-p (x)
        hellop-   (x)
        hello      (x)
        hello--   (o)
        
        ~= 독립적인 단어
        

1. 같은 엘리먼트에 2개이상의 css규칙이 적용된 경우: 우선순위가 높은 것부터 나열하시오
    1. !important
    2. 마지막규칙(맨아래)
    3. 구체적인규칙
    
    답 : 1 > 3 > 2
    

1. 다음 중 기능이 없어 자바스크립트로 동작을 구현해야 하는 것은?
    1. submit
    2. reset
    3. button
    4. image
    

답 : 3 (image -> default: submit)\

1. 각 무엇을 의미하는지 쓰시오
    
    ```jsx
    &nbsp;    공백
    &lt;       <     less than
    &gt;      >     greater than
    &amp;     &
    &quot;   "
    ```
    

1. 빈칸을 채우시오

```
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>연습문제 2</title>
  <style>
    table, td, th {
      border:1px solid #ccc;
    }
    td, th {
      padding:10px 20px;
    }
    td:last-child{
      width:200px;
    }
  </style>
</head>
<body>
  <h1>수습 국원 지원 양식</h1>

  <table>
    <tr>
      <th _______ ="3">개인정보</th>
      <th>이름</th>
      <td _______ ="2"></td>
    </tr>

    <tr>
      <th>학과/학번</th>
      <td _______ ="2"></td>
    </tr>

    <tr>
      <th>연락처</th>
      <td _______ ="2"></td>
    </tr>

    <tr>
      <th>지원분야</th>
      <td _______ ="4"></td>
    </tr>
  </table>
</body>
</html>

```

답 : 맨위 rowspan, 나머지 colspan

초급 HTML 퀴즈 5문제

Q1 HTML문서 기본 구조로 빈칸에 들어갈 올바른 말은?
(힌트 HTML문서의 필수 태그 4인방에 해당한다)

```
<!DOCTYPE html>
<[1]____>
	<[2]____>
		<[3]_____> 제목 </_____>
	</____>
	<[4]____>

	</____>
</____>

```

(1) [1]html,[2]head,[3]title,[4]main
(2) [1]html,[2]header,[3]title,[4]body
(3) [1]html,[2]head,[3]title,[4]body
(4) [1]html,[2]header,[3]name,[4]main
(5) [1]main,[2]head,[3]name,[4]body

Q2. html에서의 주석의 형태로 옳바른 것은?

(1) <!-- 주석 -->
(2) // 주석
(3) /* 주석 */
(4) #주석
(5) <%-- 주석 -->

Q3. HTML는 무엇의 약자?

(1) Hyper Transfer Markup Language
(2) Hyper Text Markup Language
(3) Hyper Typing Markup Language
(4) High Trustable Marking Language
(5) Hierarchical Templete Markup Language

Q4. 현재 W3C에서 표준으로 채택한 HTML의 버전은?

(1) HTML3
(2) HTML4.01
(3) HTML5
(4) XHTML2.0
(5) HTML6

Q5. HTML 태그 속성에 대한 설명으로 옳은 것은?

(1) 모든 HTML태그는 반드시 id라는 속성을 가져야 한다.
(2) 모든 HTML태그는 반드시 class라는 속성을 가져야 한다.
(3) 모든 HTML태그는 2개 이상의 id를 가질 수 있다.
(4) 모든 HTML태그는 2개 이상의 class를 가질 수 있다.
(5) 모든 HTML태그는 id와 class를 함께 사용할 수 없다.

중급 HTML 퀴즈 8문제

Q1. 다음 HTML 태그 중 Display value가 "Inline"인 태그는?

(1) div
(2) form
(3) input
(4) h3
(5) li

Q2.다음 HTML 태그중 Tag의 명칭과 의미가 적절하게 매칭되지 않은 것은?

(1) <ol> - 순서가 있는 리스트
(2) <th> - 테이블내 열의 제목.
(3) <style> - 내부에 CSS 코드를 입력하여 사용한다.
(4) <tr> - 테이블내 열의 각각의 원소
(5) <img> - 문서내 표시할 이미지

Q3. 다음 HTML태그중 Semantic Tag(element)에 대한 설명 적절하지 않은 것은?
(1) 모든 Semantic 태그는 display 속성이 "block"이다.
(2) "Semantic" 은 우리말로 "의미의", "의미론의" 라는 뜻을 가진다.
(3) Semantic 태그는 <section>, <article>, <footer>, <main>, <nav> 등이 있다.
(4) <article> 태그는 반드시 <section> 태그 안에 들어가야 한다. 그렇지 않으면, 화면에 제대로 표시되지 않는다.
(5) W3C에서는 가급적이면 div태그 대신, semantic 태그를 사용하기를 권장한다.

Q4. Bootstrap 5에서의 Grid에 대한 설명으로 옳지 않은 것은?

(1) 다음과 같이 "col" class는 "row" 클레스의 자식 태그에 위치해야 작동한다.

```
  <div class="row">
    <div class="col-sm-3 bg-primary text-white">.col</div>
    <div class="col-sm-3 bg-dark text-white">.col</div>
    <div class="col-sm-3 bg-primary text-white">.col</div>
    <div class="col-sm-3 bg-dark text-white">.col</div>
  </div>

```

(2) "col-lg-4" class는 span 4만큼의 비율을 가지는 column을 레이아웃에 표시하는데, 스크린의 크기가 992px보다 같거나 큰경우 사용한다.

(3) col class의 span 비율은 12등분을 기준으로 한다. 즉, col-lg-1 의 경우 row중 12분의 1을 차지하라는 의미로 해석된다.

(4) col class 내에 정의된 row는 그 자식이 해당 row가 차지하는 영역을 기준으로 새롭게 12등분하여 col의 span을 정의할 수 있다.

(5) col내 span크기를 생략할 수 있으며, 생략할 시, span 크기는 1로 고정된다.

Q5. Table내 태그의 attribute에 대한 설명으로 옳은 것은?

(1) colspan은 양 옆 테이블 셀을 합칠때 사용한다.
(2) rowspan은 위 아래 테이블 셀을 합칠때 사용한다.
(3) colspan, rowspan 모두 td, th 태그내 기입해야 한다.
(4) colspan, rowspan은 동시에 사용 할 수 없다.
(5) colspan, rowspan 모두, 기입한 만큼 각각 높이, 너비가 증가한다.

Q6. Bootstrap의 container class에 대한 설명으로 옳은 것은?

(1) container class는 기본적으로 fluid container이며, fixed container를 만들기 위해, -fixed를 붙여서 쓴다.
(2) fluid container는 width가 100%으로, 웹 사이트의 크기를 줄이고 늘릴때 마다 웹사이트 영역 width를 전부 차지하도록 조절된다.
(3) container는 패딩을 사용 할 수 있으며, pt-5를 사용할 시, 컨테이너를 기점으로 상하좌우에 5만큼 패딩을 추가한다.
(4) container는 마진을 사용 할 수 있으며, my-5를 사용할 시, 컨테이너를 기점으로 상하좌우에 5만큼의 마진을 추가한다.
(5) pt, my와 같은 패딩, 마진 클레스는 하이폰("-")과 함께 container에 붙여서 사용한다. (예: class="container-pt-5-my-5")

Q7. 다음과 같이 HTML Form이 있을때, submit 버튼을 눌렀을 때, 보내지게 되는 http request body는?

```
<form action="/ajax/login" method="post">
	<input type="hidden" id="a" value="b" class="c" name="d">
	<input type="text" id="e" value="f" class="g" name="h">
	<input type="submit">
</form>

```

(1) a=b&e=f
(2) a=d&e=h
(3) d=b&h=f
(4) c=b&g=f
(5) a=c&e=g

Q8. 하이퍼링크를 클릭했을때 새탭으로 창을 표시하게 하려고 한다. 다음중 옳바른 a 태그의 사용은?

(1) <a href="[ssafy.com/ssafy](http://ssafy.com/ssafy)" target="_blank">
(2) <a href="[ssafy.com/ssafy](http://ssafy.com/ssafy)" target="_new">
(3) <a href="[ssafy.com/ssafy](http://ssafy.com/ssafy)" target="_self">
(4) <a href="[ssafy.com/ssafy](http://ssafy.com/ssafy)" target="_parent">
(5) <a href="[ssafy.com/ssafy](http://ssafy.com/ssafy)" target="_top">

초급 HTML  정답 및 해설
Q1. (3), 필수 태그인 html, head, title, body에 대한 문제이다.
Q2. (1)
Q3. (2)
Q4. (3)
Q5. (4), id는 0또는 1개, class는 0개 이상 가질 수 있다.

중급 HTML  정답 및 정답
Q1. (3) input은 inline 태그이다.
Q2. (4) tr은 열의 원소가 아닌, 행이자, 열의 묶음에 해당한다. table row를 뜻한다. td,th에 대한 설명이다.
Q3. (4) section과 article을 제데로 구분하지 못해도 결국 렌더링시에 div로 해석하기 때문에 큰 관계는 없다. semantic tag는 말 그대로 약속이지, 특별한 기능을 하는 태그는 아니다.
별첨 : <time> 태그는 inline display를 default로 가지지만, time태그는 semantic tag로 분류 되지 않는다.
Q4. (5) 생략시, auto로 조절된다. 모든 생략한 자식 col의 너비가 같게 조정된다.
Q5. (3) 먼저 colspan rowspan은 합치는 것이 아니라, 너비 또는 높이가 2이상의 덩치가 큰 테이블 원소를 생성하는 것이다. colspan은 너비, rowspan은 높이에 해당한다. 당연히 두 개 동시에 사용 가능하다.
Q6. (2) container는 기본이 fixed이며, fluid를 사용하기위해 container-fluid를 쓴다. p가 패딩, m이 마진이며, 각각 붙이지 않고 별개의 클레스로 정의해야 한다. pt는 padding top, my는 margin y(top,bottom)에 해당한다.
Q7. (3) form은 name 속성의 값을 key로, value 속성의 값을 value로 사용한다.
Q8. (1)
