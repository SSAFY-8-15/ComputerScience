Fron-End 과목 평가 대비 문제 및 풀이 모음

1. <Form> 태그의 input 타입이 아닌 것은?
    
   1. file
   2. reset
   3. hidden
   4. click (X)
   5. image
  
2. A 태그에 대한 설명 중 틀린 것은?
    1. target의 속성 중 _blank는 링크 내용이 새창이나 새탭에서 열린다.
    2. target의 속성 중 _self는 링크가 있는 현재 윈도우에서 화면이 열린다.
    3. target을 지정하지 않으면 _self가 기본 값이다.
    4. href 속성은 URL이나 문서의 책갈피가 올 수 있다.
    5. tag를 중첩해서 사용할 수 있다. (X)
    6. 책갈피는 같은 페이지 안에서 특정요소 클릭시 그 위치로 한 번에 이동시키며 #을 붙인다.
  
3. 다음 중 CSS에 대한 설명으로 틀린 것?
    1. 선택자 (selector) : 규칙이 적용되는 요소
    2. 선언 (declaration) : 선택자에 적용될 스타일로 속성과 값으로 이루어 짐 
    3. 속성 (property) : 선택자에서 바꾸고 싶은 요소
    4. 값 (value) : 속성에 적용할 값
    5. 여러 선택자에 동일한 스타일을 적용할 때, semi-colon(;)로 구분하여 나열하며 각 속성은 comma(,)로 구분하여 나열한다.
    6. 스타일 우선순위는 인라인 스타일 > 내부 스타일 > 외부 스타일 시트 순서이다.
  
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
  
5. 다음 결과에 맞게 빈칸을 채우시오
  
    ![image](https://user-images.githubusercontent.com/79408217/190911954-dcef2d6b-3f28-4f6b-8290-7da4756a2b5a.png)
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
6. local 스토리지에 대한 설명으로 틀린 것은 (2개)
    1. 키와 값을 쌍으로 가짐
    2.  도메인과 브라우저별로 저장
    3. 값은 반드시 문자열로 저장
    4. 유효기간이 있어 브라우저를 종료시 데이터가 삭제
    5. 자바스크립트와 java로 동시에 조작
    6. 모바일에서도 사용 가능
       
       
7. 다음 중 block과 inline이 잘못 짝지어진 것은? (3개) 
    1. **<h1> - block**
    2. <p>- inline → block
    3. **<div>- block**
    4. <a> - inline
    5. **<ul>- block**
    6. <nav> - inline →block
    7. <span> - inline
    8. <input>- block →inline
    9. **<table>-block**
    10. **<form>-block**
    11. <header> - block
    
    정답:   b h f
    

8. JSON 직렬화란 무엇인지 짧게 쓰고, 직렬화에 사용하는 메소드를 적어주세요

정답:  **json→문자열,  .stringify()**




9. <div id = “ex”> 예제입니다 </div>에서, ‘예제입니다’ 라는 글자를 JS를 사용해 ‘가나다’로 바꾸고자 할 때 빈칸에 들어갈 단어는?

document.querySelector("_____").______ = “가나다”;

정답:  **#ex , innerHTML or innerText**





10. 다음 출력 값들을 작성하시오 (JS)
- console.log(100/0) = Infinity
- console.log(-Infinity / 0) = -Infinity
- console.log(0/0) = NaN ←WHY?????????
- console.log(parseInt(’1A’)) = 1 ←????????????????쓰레기언어
- console.log(”40”**+**5) = 405 문자열
- console.log(”40”-5) = 35 숫자
- console.log(”1.1”+”1.1”) = 1.11.1
- console.log((+”1.1”)+(+”1.1”)) = 2.2





11. 아래와 같은 html을  JS를 사용해 만드려고 한다.

<body>

<h2>Hello</h2>

</body>

다음 밑줄에 들어갈 말은?

var title = document.createElement(’h2’);

var msg = document.createTextNode(’Hello’);

title.___________(msg);

document.body.________(title);

정답: 둘 다 **appendChild**






12. id값이 third인 부분을  JS를 사용해 지우려고 한다

<body>

<h2 id=”first”>Hello</h2>

<h2 id=”second”>Hello</h2>

<h2 id=”third”>Hello</h2>

</body>

다음 밑줄에 들어갈 말은?

document.body._______(____);

정답:**removeChild('#third')**





  
