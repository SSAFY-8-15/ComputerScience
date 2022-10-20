1. 객체지향프로그래밍 SOLID 설명에서 두개의 틀린 것을 찾고 바꾸세요

- | S | SRP
- 단일 책임 원칙 (Single responsibility principle) | - 한 클래스는 하나의 책임만 가져야 한다.
- | O | OCP
- 개방-폐쇄 원칙 (Open/closed principle) | - “소프트웨어 요소는 확장에는 열려 있으나 변경에는 닫혀 있어야 한다.”
- | L | LSP
- 리스코프 치환 원칙 (Liskov substitution principle) | - “프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 한다.” 
- | I | ISP
- 인터페이스 분리 원칙 (Interface segregation principle) | - “특정 클라이언트를 위한 인터페이스 한 개가 범용 인터페이스 여러 개보다 낫다.” 
- | D | DIP
- 의존관계 역전 원칙 (Dependency inversion principle) | - 프로그래머는 “구체화에 의존해야지, 추상화에 의존하면 안된다.” 

2.빈에서

컨테이너가 항상 새로운 인스턴스를 반환하게 만들고 싶을경우 scope를 ‘    ‘로 설정해야함

1) singleton

2)request

3) session

4) global session

5) prototype

3. 요청발생 과정중에 빈칸을 채우세요(빈칸 다 똑같음)

1) 요청 발생

2)dispatcher servlet 실행

3) handler mapping 을 활용하여 해당 요청을 처리할 ‘        ‘ 을 찾아온다

4)’         ‘  에게 요청 처리 위임

5) ‘       ‘가 작업한 이후에 modelAndView 리턴

6) modelAndView가 정해지지 않았다면 ViewResolver를 사용하며 View를 찾아온다

modelAndView를 통해 view가 정해졌다면 viewResolver를 통해 view를 찾지 않는다.

7) view에게 rendering시킴

8) view가 rendering한 내용이 응답으로 전송

4. Spring Bean 주요 속성 정의중 알맞지 않은것은?
1) name : 정규화된 자바 클래스 이름
2) id: bean의 고유 식별자
3) scope: 객체의 범위 (sigleton, prototype)
4) constructor-arg: 생성 시 생성자에 전달할 인수
5) property: 생성 시 bean setter에 전달할 인수
6) init method와 destroy method

5. spring과 springboot차이중 틀린점
- 1) Embed Tomcat을 사용하기 때문에, (Spring Boot 내부에 Tomcat이 포함되어있다.) 따로 Tomcat을 설치하거나 매번 버전을 관리해 주어야 하는 수고로움을 덜어준다.
- 2) starter을 통한 dependency 자동화 : 아마 Spring 유저들이 가장 열광한 기능이 아닐까 싶다. 과거 Spring framework에서는 각각의 dependency들의 호환되는 버전을 일일이 맞추어 주어야 했다 
- 하지만, 이제 starter가 대부분의 dependency를 관리해주기 때문에 이러한 걱정을 많이 덜게 되었다.
- 3) XML설정을 기본 하나만 하면 된다.
- 4) jar file을 이용해 자바 옵션만으로 손쉽게 배포가 가능하다.Spring Actuaor를 이용한 애플리케이션의 모니터링과 관리를 제공한다.
