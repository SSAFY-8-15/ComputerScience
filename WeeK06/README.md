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
       
  
