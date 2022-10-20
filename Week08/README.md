Q1) DI 방법 3가지는 무엇인가요?
	Field Injection, Setter Injection, Constructor Injection

Q2) Bean들이 싱클턴패턴의 특징을 가지는 이유는 무엇인가요?
	Spring에서는 Bean들을 Spring Container에서 생성되는데 모두 싱글턴으로 관리됨, scope의 기본값이 singleton이다.

Q3) 스프링에서 DB에 접근하여 실제 데이터를 조회/조작하는 클래스(DAO 역할)는 무엇인가요?
	Repository 또는 Mapper


Q4) MVC 진행 방식을 순서대로 골라주세요

	A. 클라이언트로부터 요청이 들어오면 dispatcherServlet이 가장 먼저 받는다.

	B. ViewResolver에서 controller가 리턴한 view 검색 후 view를 클라이언트로 보낸다.

	C. HandlerAdapter에서 알맞은 controller 처리 요청한다.

	D. HandlerMapping이 요청 url 과 매핑되는 Controller 검색 후 리턴한다.

Q5) DI 가 하는 일이 아닌 것은

	A. 필드 주입

	B. 제네릭 주입

	C. setter 주입

	D. 생성자 주입
	
	
	
Q6) 스프링에는 의존성 주입(DI)이란 제어 역전(IoC)의 방법 중 하나로 사용할 객체를 직접 생성하지 않고 외부 컨테이너가 생성한 객체를 주입 받아 사용하는 방식을 의미합니다. 

그렇다면 이 객체를 주입하는 방법 3가지와 그 중 스프링에서 권장하는 방법은? 

1. 
2. 
3.

Q7) 스프링 컨테이너에 대한 설명으로 틀린 것은?


1. 객체의 생성 사용 소멸에 해당하는 Life Cycle을 담당한다.
2. Thread를 관리한다.
3. 서비스 객체를 사용하기 위한 Factory, Singleton 패턴을 개발자가 직접 구현하지 않아도 되게 해준다.
4. 컨테이너가 코드 대신 객체에 대한 제어권을 갖고 있어 IoC 컨테이너라고도 불린다.
5. BeanFactory는 ApplicationContext를 상속 받는다.


Q8) 스프링 빈에서 Stereotype annotation 종류 4가지는?
1.
2.
3.
4.

Q8) 객체지향프로그래밍 SOLID 설명에서 두개의 틀린 것을 찾고 바꾸세요

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

Q9) 빈에서 컨테이너가 항상 새로운 인스턴스를 반환하게 만들고 싶을경우 scope를 ‘    ‘로 설정해야함

1) singleton

2) request

3) session

4) global session

5) prototype




Q10) 요청발생 과정중에 빈칸을 채우세요(빈칸 다 똑같음)

[1] 요청 발생

[2] dispatcher servlet 실행

[3] handler mapping 을 활용하여 해당 요청을 처리할 ‘        ‘ 을 찾아온다

[4] __________ 에게 요청 처리 위임

[5] __________ 가 작업한 이후에 modelAndView 리턴

[6] modelAndView가 정해지지 않았다면 ViewResolver를 사용하며 View를 찾아온다
	modelAndView를 통해 view가 정해졌다면 viewResolver를 통해 view를 찾지 않는다.

[7] view에게 rendering시킴

[8] view가 rendering한 내용이 응답으로 전송

Q11) Spring Bean 주요 속성 정의중 알맞지 않은것은?
1) name : 정규화된 자바 클래스 이름
2) id: bean의 고유 식별자
3) scope: 객체의 범위 (sigleton, prototype)
4) constructor-arg: 생성 시 생성자에 전달할 인수
5) property: 생성 시 bean setter에 전달할 인수
6) init method와 destroy method

Q12). spring과 springboot차이중 틀린점

1) Embed Tomcat을 사용하기 때문에, (Spring Boot 내부에 Tomcat이 포함되어있다.) 따로 Tomcat을 설치하거나 매번 버전을 관리해 주어야 하는 수고로움을 덜어준다.
2) starter을 통한 dependency 자동화 : 아마 Spring 유저들이 가장 열광한 기능이 아닐까 싶다. 과거 Spring framework에서는 각각의 dependency들의 호환되는 버전을 일일이 맞추어 주어야 했다 
		하지만, 이제 starter가 대부분의 dependency를 관리해주기 때문에 이러한 걱정을 많이 덜게 되었다.
3) XML설정을 기본 하나만 하면 된다.
4) jar file을 이용해 자바 옵션만으로 손쉽게 배포가 가능하다.Spring Actuaor를 이용한 애플리케이션의 모니터링과 관리를 제공한다.




Q13) 스프링 동작방식

[1]DispatcherServlet이 브라우저로부터 요청을 받는다.
[2]DispatcherServlet은 요청된 URL을 __________객체에 넘기고,
호출해야 할 Controller 메소드 정보를 얻는다.

DispatcherServlet이 HandlerAdapter 객체를 가져온다.

HandlerAdapter 객체의 메소드를 실행한다.

Controller 객체는 비즈니스 로직을 처리하고, 그 결과를 바탕으로 뷰(ex. JSP)에 전달할 객체를 Model 객체에 저장한다. DispatcherServlet에게 view name을 리턴한다.

DispatcherServlet은 view name을 _________에게 전달하여 View 객체를 얻는다.

DispatcherServlet은 View 객체에 화면 표시를 의뢰한다.

View 객체는 해당하는 뷰(ex. JSP, Thymeleaf)를 호출하며,

뷰는 Model 객체에서 화면 표시에 필요한 객체를 가져와 화면 표시를 처리한다.

스프링 컨테이너는 등록된 스프링 빈을 _____패턴으로 생성하고 관리한다. 각 메서드에 @____을 붙여 스프링 컨테이너에 스프링 빈으로 등록할 수 있다.

필터와 인터셉터는 Web Spring영역에 있다. (O/X)

인터셉터 인터페이스의 메소드 3가지 중에 컨트롤러가 호출된 후에 불리게 되는 2가지 메소드를 말하고, 둘의 차이를 간단하게 서술
