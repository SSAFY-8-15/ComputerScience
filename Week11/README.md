
---
# 강승권
## 객관식 문제 1

다음 코드의 실행결과로 출력된 로그가 <b>보기</b>와 같도록 하려고 한다. 



```javascript
[project/router/index.js]
import App from  "@/views/App";

Vue.use(VueRouter);

const  routes  = [
	path:  "/helloworld/:hello",
	name:  "helloworld",
	component: App
}
```

```html
[project/views/App.vue]
<template>
	<div>
	</div>
</template>
<script>
	export  default  {
		name:  "AppUser",
		mounted(){
			console.log(_________);
		}
	};

</script>
```


<b>보기</b>

```bash
[http://localhost:8081/helloworld/hello]
>> hello
```

빈칸에 넣을 말로 올바른 것은?

```javascript
1. this.$route.query.hello

2. this.$router.query.hello

3. this.$route.params.hello

4. this.$router.params.hello
```

<details>
<summary>정답보기</summary>
정답  : 3 <br/>
$router는 전체 라우터, $route는 현재 라우터, <br/>
query는 querystring의 형태로 ?hello=hello의 형태를 취해야 한다.<br/>
params는 :paramKey의 형태로 받아올 수 있다.<br/>
</details>

---


## 객관식 문제 2

자식 컴포넌트에서 부모 컴포넌트의 함수 updateContent을 호출하려고 한다.



```javascript
...
methods : {
	notifyContent(e) {
		this.$______('updateContent', e.target.value);	
	}
}
...
```

빈칸에 넣을 말로 올바른 것은?

```javascript
1. emit

2. on

3. route

4. refs
```

<details>
<summary>정답보기</summary>
정답  : 1 <br/>
$emit 을 통해 부모 컴포넌트의 메소드를 호출 할 수 있다. <br/>
$on은 이벤트리스너의 형태로 등록하여 이벤트를 감지할때 쓰인다. 이벤트 발생전까지 호출되지 않는다. <br/>
</details>


---


## 객관식 문제 3

컴포넌트에 있는 data중 articles가 비어있을때 <b>#myDiv</b> 영역의 <i>style</i>에
```css 
display: none;
``` 
의 효과를 주려고 한다.

```html
<template>
	<div ______="articles.length" id="myDiv">
		...
	</div>
</template>
```

빈칸에 넣을 말로 올바른 것은?

```
1. v-cloak

2. v-if

3. v-show

4. v-hide
```

<details>
<summary>정답보기</summary>
정답  : 3 <br/>
v-show의 결과가 false일시, 해당 블록내 display를 none으로 변화시킨다. <br/>
</details>


---


## 객관식 문제 4

다음 코드의 출력 결과로 옳은 것은?

```html
<script>
	let  vm  =  new  Vue({
		data:  {
			a:  1,
		},
		computed:  {
			minusA()  {
				console.log('a');
				return  -this.a;
			},
			plusA:  {
				get()  {
					console.log('b');
					return  this.a;
				},
				set(v)  {
					console.log('c');
					this.a  =  v;
				},
			},
		},
	});
	
	let  a  =  vm.minusA +  vm.minusA;
	let  b  =  vm.plusA +  vm.plusA;
	vm.plusA =  vm.plusA +  10;
	let  c  =  vm.minusA +  vm.plusA;
</script>
```


```javascript
1. aabbcab

2. abcab

3. aabcab

4. abbcab

5. 네.. 네? 뭐..뭐라고요?
```

<details>
<summary>정답보기</summary>
정답  : 2 <br/>
computed의 setter는 항상 호출된다. getter는 내부에서 명시적으로 호출하는 data가 변하지 않았다면 메소드는 호출되지 않으며, 대신 캐싱된 데이터의 값을 가져온다. <br/>
</details>



## 객관식 문제 5


```
______ 는 추가 HTTP 헤더를 사용하여, 
한 출처에서 실행 중인 웹 애플리케이션이 다른 출처의 선택한 자원에 접근할 수 있는 권한을 부여하도록 
브라우저에 알려주는 체제입니다. 

웹 애플리케이션은 리소스가 자신의 출처(도메인, 프로토콜, 포트)와 다를 때 교차 출처 HTTP 요청을 실행합니다.
```

빈칸에 넣을 말로 올바른 것은?

```java
1. COSP (Cross-Origin Sharing Policy)

2. CORP (Cross-Origin Resource Permition)

3. CORS (Cross-Origin Resource Sharing)

4. CORB (Cross-Origin Read Blocking)

5. ISBM (Igger Sihum Bumwi Maja?)
```

<details>
<summary>정답보기</summary>
정답  : 3 <br/>
교차출처 리소스 공유(CORS)에 대한 설명이다.<br/>
교차출처 읽기방지 (CORB)와 햇갈리지 않도록 주의한다.<br/>
</details>


## 객관식 문제 6

div#app 아래 모든 체크박스를 checkedAreas와 <b>양방향 바인딩</b> 설정하려고 한다. 

```html
<body>
	<div id="app">
		<div>당신이 가고 싶은 지역을 선택하시오</div>
		<input  type="checkbox" id="buk" value="부울경" ______="checkedAreas" />
		<label  for="buk">부울경</label>
		<input  type="checkbox" id="gwangju" value="광주" ______="checkedAreas" />
		<label  for="gwangju">광주</label>
		<input  type="checkbox" id="gumi" value="구미" ______="checkedAreas" />
		<label  for="gumi">구미</label>
		<input  type="checkbox" id="daejeon" value="대전" ______="checkedAreas" />
		<label  for="daejeon">대전</label>
		<input  type="checkbox" id="seoul" value="서울" ______="checkedAreas" />
		<label  for="seoul">서울</label>
		<br />
		<span>체크한 이름: {{ checkedAreas }}</span>
	</div>
	<script>
		new  Vue({
			el:  '#app',
			data:  {
				checkedAreas: [],
			},
		});
	</script>
</body>
```
빈칸에 들어갈 말로 적절한 것은?
```java
1. v-on

2. v-bind

3. v-set

4. v-model
```

<details>
<summary>정답보기</summary>
정답  : 4 <br/>
v-model을 통해 view-model간 양방향 바인딩을 설정할 수 있다.<br/>
</details>

---

## 객관식 문제 7

vue 디렉티브 
```js
v-on:click="abc" 
v-bind:src="def"
```

와 동일한 기능을 하는 것으로 올바른 것은?

```html
1. 
	@click="abc" 
	:src="def"
2.
	@click="abc" 
	$src="def"
3. 
	#click="abc" 
	:src="def"
4.
	#click="abc" 
	$src="def"
```

<details>
<summary>정답보기</summary>
정답  : 1 <br/>
이벤트 바인딩 v-on은 @로,  model data바인딩 v-model은 :로 줄일 수 있다. <br/>
</details>

---

## 객관식 문제 8

다음 코드의 실행결과, 콘솔창에 뜨게 될 결과로 옳은 것은?
```html
<body>
	<div  id="app">
		<div id="hello">정답은 1번!</div>
		<div ref="hello">정답은 2번!</div>
		<div name="hello">정답은 3번!</div>
	</div>
	<script>
		new  Vue({
			el:  '#app',
			created(){
				console.log(this.$refs.hello.innerText);
			}
		});
	</script>
</body>
```

```html
1. 정답은 1번!
2. 정답은 2번!
3. 정답은 3번!
4. 런타임 에러
```

<details>
<summary>정답보기</summary>
정답  : 4 <br/>
created 단계의 Lifecycle Hook에서는 dom이 생성되지도, 렌더링 되지 않았으므로, 접근할 수 없다. <br/>
created대신, mounted를 사용하게 되면, 정상적으로 정답은 2번!이 호출된다.<br/>
</details>

---

## 객관식 문제 9

다음 코드의 실행결과, 브라우저에서 볼 수 있는 내용으로 적절한 것은?
```html
<body>
	<div  id="app">
		<div  v-text="'메세지 : ' + message"></div>
	</div>
	<script>
		new  Vue({
			el:  '#app',
			data:  {
				message:  '<h2>Hello Vue~!</h2>',
			},
		});
	</script>
</body>
```

```html
1. 메세지 : + message

2. 메세지 : <h2>hello Vue~!</h2>

3. 메세지 : Hello Vue~!

4. `메세지 : ` + message
```

<details>
<summary>정답보기</summary>
정답  : 2 <br/>
v-text는 내부 html이 아닌 text의 형태로 인코딩한 결과를 출력한다. <br/>
v-text 및 v-html은 v-bind처럼 vue내 data객체를 참조하여 처리한다.<br/>
</details>

---

## 객관식 문제 10

Vue.js의 필터에 관한 설명으로 <u>옳지 않은</u> 것은?

```html
1. 화면에 표시되는 텍스트의 형식을 쉽게 변환해주는 기능을 가진다.

2. 지역필터 및 전역필터의 형태로 정의 가능하다.

3. 지역필터의 경우 Vue instance중 filters내부에 정의한다.

4. 중괄호 보간법 [ {{}} ] 또는 v-text 속성에서 사용 가능하다.
```

<details>
<summary>정답보기</summary>
정답  : 4 <br/>
v-text에서는 사용 할 수 없다.  <br/>
중괄호 보간법 [ {{}} ] 또는 v-bind 속성에서 사용 가능하다. <br/>
</details>

---


## 주관식 문제 1


SPA에 대해 설명하시오.


<details>
<summary>정답보기</summary>
정답  : <br/>
서버로부터 완전한 새로운 페이지를 불러오지 않고 현재의 페이지를 동적으로 다시 작성함으로써 사용자와 소통하는 웹 어플리케이션이나 웹사이트를 말한다. <br/>
</details>

---



## 주관식 문제 2

빈칸에 들어갈 말로 적절한 것은?

```
Vue.js는 MVVM 패턴을 사용한다. MVVM 패턴에서의 3가지 주요 모듈로 __(A)__, __(B)__, __(C)__이 있다.

html, css가 __(A)__ 영역에 속하며,
javascript, data영역이 __(C)__에 속하며,
Vue의 영역이 __(B)__에 속한다.
```

<details>
<summary>정답보기</summary>
정답  : <br/>
(A) : View, (B) : ViewModel, (C) : Model<br/>
</details>

---


## 주관식 문제 3

Vue Lifecycle Hooks 메소드를 3개 이상 쓰시오, 단, 작성시 작동 순서가 정해져 있는 경우 작동 순서 순으로 작성하시오. 

<details>
<summary>정답보기</summary>
정답  : <br/>
beforeCreate -> created -> beforeMount -> mounted -> beforeUpdate -> updated -> beforeDestroy -> destroyed
</details>

---


## 주관식 문제 4

변수의 네이밍컨벤션에는 camel 표기법, Pascal 표기법, Snake 표기법, Kebab 표기법등이 있다.

아래는 camel 표기법으로 명명된 변수이다.

```js
	let countOfData = ....
```

위 변수를 Pascal 표기법, Kebab 표기법의 형태로 바꾼 결과를 작성하시오.


<details>
<summary>정답보기</summary>
정답  : <br/>
	Pascal 표기법 : CountOfData,  Kebab 표기법 : count-of-data
</details>

---


## 주관식 문제 5

클릭시 sendMsg1 이외에 다른 이벤트의 호출을 방지하려고 한다.

```html
	<a  href="test29.html" @click._______="sendMsg1">페이지 이동 막기</a><br/>
```

빈칸에 들어갈 말로 올바른 것은?


<details>
<summary>정답보기</summary>
정답  : <br/>
	prevent
</details>

---

## 주관식 문제 6



다음 텍스트상자내 데이터를 집어넣으려고 한다.

v-model은 기본적으로 모든 key stroke가 발생할 때마다 값을 업데이트 시킨다.

그러나, 매 key stroke 대신, change 이벤트 이후에 동기화를 하도록 하려고 한다.

```html
	<input  v-model._____="id" placeholder="Input Text..." />
```

빈칸에 들어갈 말로 올바른 것은?


<details>
<summary>정답보기</summary>
정답  : <br/>
	lazy
</details>

---


## 주관식 문제 7



빈칸에 들어갈 말로 올바른 것은?

```
______는 ECMA 6에서 도입된 객체로, 비동기 작업이 맞이할 미래의 완료 또는 실패와 그 결과 값을 나타낸다.
______를 사용하면 비동기 메서드에서 마치 동기 메서드처럼 값을 반환할 수 있다. 

_____는 다음 중 하나의 상태를 가집니다.

- 대기(_pending): 이행하지도, 거부하지도 않은 초기 상태.
- 이행(_fulfilled): 연산이 성공적으로 완료됨.
- 거부(_rejected): 연산이 실패함.

대표적으로  ______를 기반으로 한 비동기 통신 라이브러리 javascript Axios가 있다.
```


<details>
<summary>정답보기</summary>
정답  : <br/>
	Promise
</details>

---

## 주관식 문제 8

Vue.js에서 router를 통해 페이지 이동시 페이지 컴포넌트를 출력하는 위치를 지정하고 싶다.

```html
<html>
  <body>
    <div id="app">
      <router-link to="apple">apple</router-link>
      <router-link to="google">google</router-link>
      <_________></_________>
    </div>
  </body>
</html>
```

해당 빈칸이 있는 위치로 출력 위치를 지정하기 위해 빈칸에 들어갈 말로 적절한 것은?


<details>
<summary>정답보기</summary>
정답  : <br/>
	router-view
</details>

---

## 주관식 문제 9


부모 컴포넌트에서 자식 컴포넌트로.  변수 article을 단방향 바인딩의 형태로 전달하려고 한다.

```html
	[BoardList.vue]
<board-list-item  
	v-for="article in articles"
	:key="article.articleno"  
	:article="article">
</board-list-item>
```

```html
[BoardListItem.vue]
	...
<script>
	export  default  {
		name:  "BoardListItem",
		______:  {
			article:  Object,
		},
	};
</script>
```

빈칸에 들어갈 말로 적절한 것은?


<details>
<summary>정답보기</summary>
정답  : <br/>
	props
</details>

---


## 주관식 문제 10


Vue Instance내 들어갈 수 있는 모든 Option을 아는대로 쓰시오. (3개이상)


<details>
<summary>정답보기</summary>
정답  : <br/>
	el,name,props,lifecycle Hooks, filters, watch, computed, methods
</details>

---
# 
# 11.14 Vue 과목평가대비

Q1. 다음 중 옳은 것은?(2개)

1. SPA(SinglePageApplication) 여러개로 .html 1개 SFC(SingleFileComponent)을 구성한다
2. Component끼리는 대화가 가능하지만 객체 전달은 불가능하다           ⇒ 객체전달가능함^^
3. 데이터 바인딩의 가장 기본 형태는 {{ }} Mustache 구문을 이용한 텍스트 보간이다.
4. v-bind는 약어로 : 으로 사용가능하다.

A) 3, 4

---

Q2. 다음 중 설명이 틀린것은?

1. v-text : HTML의 태그가 적용되지 않고 문자열이 그대로 보``여진다
2. v-once : 데이터 변경 시 업데이트가 되지 않는 일회성 보간 수행
3. v-bind : 뷰 인스턴스와 양방향으로 바인딩해서 뷰 인스턴스의 data 또는 input 태그를 통해 바인딩한 값을 수정할 수 있다
4. v-cloak : Vue Instance가 준비될 때까지 mustache 바인딩을 숨기는 데 사용한다

A) 3번 v-model에 관한 설명이다

---

Q3. v-if, v-show의 조건문 결과가 false일 때 어떤 점이 다른가?

A) v-if : 객체 생성이 안됨. v-show: 객체생성됨

우선 `v-if`는 조건에 따라 컴포넌트가 **실제로** 제거되고 생성된다.

반면에 `v-show` 는 단순히 `css` 의 `display` 속성만 변경된다

---

Q4. vue.js는 MVVM 패턴(____ + _____ + _____)을 사용한다. 빈칸을 채우시오 (무엇의 약자인지)

A) Model View ViewModel

---

Q5. 다음 중 Vue Instance에 속하는 속성이 아닌 것은?

1. el
2. methods
3. filters
4. watch
5. destroy

A) 5번

---

Q6. LifeCycle은 크게 4단계로 나눌수있다. 각 단계는?
1. created 생성 
2. mounted 부착 
3. updated 변경 
4. destroyed 소멸

A) created mounted updated destroyed 생성 부착 변경 소멸

---

Q7. 다음 중 틀린 것은?

1. function 앞에 async 키워드를 추가하면 함수는 언제나 promise를 반환한다.
2. promise 앞에 await 키워드를 붙이면 promise가 처리 될 때까지 대기한다.
3. await는 async 함수 밖에서도 사용이 가능하다
4. await async는 .then 반복을 방지하기 위해 사용한다

A) 3번

---
# 
1. Vue.js에서 사용하는 디자인패턴이란 무엇인가요? 그리고 각 알파벳이 의미하는 걸 서술하세요
    1. MVVM (Model + View + View Model)
    
---
    
2.  뷰 인스턴스의 속성 중에 ‘Vue가 적용될 요소를 지정”하는 속성은?
    
    1)el
    
    2)data
    
    3)template
    
    4)methods
    
    1. el - Vue가 적용될 요소 지정. CSS Selector or HTML Element

---

3. SPA와 SFC의 스펠링은?
    1. Single Page Application
    2. Single FIle Component

---

4. SFC의 3요소
    1. templete, script, style

---

5. 클릭이벤트의 기본 기능을 막기 위한 방법 중 맞는 것 2가지를 고르세요
    1. <a href=”주소” @click.prevent=”함수1”></a>
    2. <a href=”주소” @click.preventDefault=”함수1”></a>
    3. <a href=”주소” @click.preventDefault(함수1)></a>
    4. 함수2(e){
        
        e.preventDefaultEvent();
        
        }
        
    5. 함수2(e){
        
        e.preventDefault();
        
        }
        
    
    f. 함수2(e){
    
    e.prevent();
    
    }  
    
    →A E

---

6.  뷰 인스턴스 속성 중에 다음 설명에 해당하는 것은?
    
    <특정 데이터의 변경사항을 실시간으로 처리>
    
    <캐싱을 이용하여 데이터의 변경이 없을 경우 캐싱된 데이터를 반환한다>
    
    <Setter와 Getter를 직접 지정할 수 있다>
    
    1. 정답: Computed
    2. Computed의 함수 호출시에는 property를 쓰지 않는다. → ()가 없는 것을 말함.
        
        {{ reversedMsg }} , {{ reversedMsg() }} 
        
---

7.  computed와 watch의 차이?
    1. Computed는 종속된 data가 변경되었을 경우 그 data를 다시 계산하여 캐싱한다.
    2. Watch는 data가 변경되는지 감시하고 있다가 변경되었을 경우 실행되어, 다른data를 변경하는 작업을 한다.

---

8. LifeCycle 8가지 속성 스펠링을 모두 쓰세요
    1. beforeCreate, created, beforeMount, mounted, beforeUpdate, updated, beforeDestroy, destroyed

---

9. 자식-부모간 컴포넌트간 통신은 단방향으로만 가능하다. 두 컴포넌트간 통신 방식을 간단하게 서술하세요.
    1. 자식→부모 emit 이벤트를 발생시켜 전달.
    2. 부모→자식 props를 전달

---

---
# 임민수
1) 뷰의 필터는 어떠한 속성 AND 법에서 사용이 가능할까요??(2가지)

A) 중괄호 보간법{{}} , v-bind 속성

---

2)form 수식어에 대하여 틀린거

1 - lazy : change 이벤트 이후에 동기화하기를 원할 때

2 - number : 숫자로 형변환 되기를 원할 때

3- trim : 자동으로 공백을 추가하길 원할 때 

A)3 - 제거하길 원할 때 

---

3)HTTP헤더를 사용해서 어떠한 출처에서 에서 실행 중인 웹 애플리케이션이 다른 출처의 선택한 자원에 접근할 수 있는 권한을 부여하도록 브라우저에 알려주는 체제는 무엇일까요?

A) CORS

---

4) 전역컴포넌트를 등록하려면 [1] 를 쓰고 권장 표기법은 [2]다,

 지역컴포넌트를 등록하려면 [3] 를 인스턴스 옵션으로 등록한다 뭘까요??

A) Vue.component, kebab , components

---

5) 사용자 정의 이벤트 발생할때는 $[1] 쓰고, 이벤트 수신할때는 $[2] 쓰는데 무엇일까요???

A) emit / on

---
