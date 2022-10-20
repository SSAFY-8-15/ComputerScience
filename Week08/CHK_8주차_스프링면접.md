# #6. Spring 면접 대비 CS 정리

## 스프링 프레임워크란?

![https://blog.kakaocdn.net/dn/OGYGM/btrlEIsmmn6/KSjuU8NlCDovtM1ke0yFj0/img.png](https://blog.kakaocdn.net/dn/OGYGM/btrlEIsmmn6/KSjuU8NlCDovtM1ke0yFj0/img.png)

- 자바(JAVA) 플랫폼을 위한 오픈소스 애플리케이션 프레임워크이다.
- 자바 엔터프라이즈 개발을 편하게 해주는 **오픈소스 경량 애플리케이션 프레임워크**이다.
- 동적인 웹 사이트 개발하기 위한 여러 가지 서비스를 제공함
- 대한민국 공공기관의 웹 서비스 개발 시 사용을 권장하고 있는 전자정부 표준프레임워크의 기반 기술.
- 자바 개발을 위한 프레임워크로 종속 개체를 생성해주고, 조립해주는 도구

## 스프링프레임워크 특징

- **DI (Dependency Injection) 의존성 주입**: 설정 파일이나 어노테이션을 통해 객체간의 의존 관계를 설정하여 개발자가 직접 의존하는 객체를 생성할 필요가 없다. 개발코드 부분에서 객체를 생성하는 것이 아니라, 데이터 주입만 담당하는 별도의 공간에서 객체를 생성하고, 데이터 간의 의존성을 주입해 개발코드에서 가져다 쓰면서 의존성을 줄인다. 필드 주입, setter 주입, 생성자 주입 3가지가 있다.
- **AOP(Aspect Oriented Programming) 관점 지향 프로그래밍**: 어떤 로직을 기준으로 핵심적인 관점, 부가적인 관점으로 나누어서 보고 그 관점을 기준으로 각각 모듈화 하겠다는 것이다. 트랜잭션, 로깅, 보안 등 여러 모듈, 여러 계층에서 공통으로 필요로 하는 기능의 경우 중복코드를 방지하기 위해 해당 기능을 분리해 관리하고, 실행시 비즈니스 로직의 앞과 뒤에서 원하는 지점에 해당 공통 관심사를 수행할 수 있게 한다.
- **POJO(Plain Old Java Object)**: 객체 지향적인 원리에 충실하면서, 환경과 기술에 종속되지 않고 필요에 따라 재활용될 수 있는 방식으로 설계된 오브텍트를 말한다. 일반적인 J2EE 프레임워크에 비해 특정 라이브러리를 사용할 필요가 없어 개발이 쉽다. 기존 라이브러리의 지원이 용이하다.
- **IoC(Inversion of Control) 제어 반전**: 컨트롤의 제어권이 개발자가 아니라 프레임워크에 있다. 객체의 생성부터 모든 생명주기의 관리까지 프레임워크가 주도하고 있다. 객체를 생성하고, 직접 호출하는 프로그램이 아니라, 만들어둔 자원을 호출해서 사용한다. 인스턴스의 생성의 제어를 서블릿과 같은 bean을 관리해주는 컨테이너가 관리한다.

## 객체지향적 설계 원칙 (SOLID)

- SRP(Single Responsibility Principle) : 단일 책임 원칙. 클래스는 단 하나의 책임을 가져야 하며 클래스를 변경하는 이유는 단 하나의 이유이어야 한다.
- OCP(Open-Closed Principle) : 개방-폐쇄 원칙. 확장에는 열려 있어야 하고 변경에는 닫혀 있어야 한다.
- LSP(Liskov Substitution Principle) : 리스코프 치환 원칙/ 상위 타입의 객체를 하위 타입의 객체로 치환해도 상위 타입을 사용하는 프로그램은 정상적으로 동작해야 한다.
- ISP(Interface Segregation Principle) : 인터페이스 분리 원칙. 인터페이스는 그 인터페이스를 사용하는 클라이언트를 기준으로 분리해야 한다.
- DIP(Dependency Inversion Prinsiple) : 의존 역전 원칙. 고수준 모듈은 저수준 모듈의 구현에 의존해서는 안된다.

## **스프링 컨테이너란?**

- 스프링에서 사용할 객체들을 담고있는 것.
- ApplicationContext(인터페이스)를 스프링 컨테이너라 한다.
- 등록된 스프링 빈을 생성하고 의존관계를 주입하고 생명주기를 관리해준다.
- AppConfig에 설정을 구성한다는 뜻의 @Configuration 어노테이션을 붙인다.
- 각 메서드에 @Bean을 붙여 스프링 컨테이너에 스프링 빈으로 등록할 수 있다.
- 스프링 컨테이너는 등록된 스프링 빈을 싱글톤 패턴으로 생성하고 관리한다.

## Bean이란?

- spring IoC 컨테이너가 관리하는 자바 객체를 빈(Bean)이라는 용어로 부른다. 우리가 new 연산자로 어떤 객체를 생성했을 때 그 객체는 빈이 아니다.
- 즉 스프링 컨테이너가 생성한 객체들을 '빈'이라고 한다.

## Spring 동작방식이란?

![https://velog.velcdn.com/images%2Fkk1112k%2Fpost%2F3000060c-c897-4244-937c-f833d6c41b07%2Fimage.png](https://velog.velcdn.com/images%2Fkk1112k%2Fpost%2F3000060c-c897-4244-937c-f833d6c41b07%2Fimage.png)

1. DispatcherServlet이 브라우저로부터 요청을 받는다.

2. DispatcherServlet은 요청된 URL을 HandlerMapping 객체에 넘기고,

호출해야 할 Controller 메소드(핸들러) 정보를 얻는다.

3. DispatcherServlet이 HandlerAdapter 객체를 가져온다.

4. HandlerAdapter 객체의 메소드를 실행한다.

5. Controller 객체는 비즈니스 로직을 처리하고, 그 결과를 바탕으로 뷰(ex. JSP)에 전달할 객체를 Model 객체에 저장한다. DispatcherServlet에게 view name을 리턴한다.

6. DispatcherServlet은 view name을 View Resolver에게 전달하여 View 객체를 얻는다.

7. DispatcherServlet은 View 객체에 화면 표시를 의뢰한다.

8. View 객체는 해당하는 뷰(ex. JSP, Thymeleaf)를 호출하며,

뷰는 Model 객체에서 화면 표시에 필요한 객체를 가져와 화면 표시를 처리한다.

## MVC 진행 방식

- 클라이언트로부터 요청이 들어오면 dispatcherServlet이 가장 먼저받는다.
- HandlerMapping이 요청 URL과 매핑되는 Controller 검색 후 리턴
- HandlerAdapter에서 알맞은 controller 처리요청
- ViewResolver에서 controller가 리턴한 view 검색후 view를 클라이언트로 보냄

![https://blog.kakaocdn.net/dn/q6N22/btq6w7SYSsc/2HTvaBQTnqF857n7b86N3K/img.png](https://blog.kakaocdn.net/dn/q6N22/btq6w7SYSsc/2HTvaBQTnqF857n7b86N3K/img.png)

## 공통처리

스프링 코드를 작성할 때 공통적으로 처리해야할 업무들이 많다. 공통업무에 관련된 코드를 모든 페이지 마다 작성해야한다면 중복된 코드가 많아지게 되면 소스관리가 힘들어진다.

즉, 공통처리를 위해 활용할 수 있는 것이 3가지가 있다.

1. Filter
2. Interceptor
3. AOP

## 스프링 필터 VS 인터셉터

- 실행되는 시점에서 차이가 있다. 필터는 dispatcherServlet으로 요청이 가기전에 실행되고 인터셉터는 Controller로 요청이 가기전에 실행된다.
- 따라서 컨트롤러에 들어가기 전 작업을 처리하기 위해 사용하는 공통점이 있지만, 호출되는 시점에서 차이가 존재한다.

## **필터(Filter)**

필터는 J2EE 표준 스펙 기능으로 디스패처 서블릿(Dispatcher Servlet)의 앞단에서 정보를 처리한다.

디스패처 서블릿은 스프링의 가장 앞단에 존재하는 프론트 컨트롤러이므로, 필터는 스프링 범위 밖에서 처리가 되는 것이다.

스프링 컨테이너에 존재하는 빈들을 사용할 수 없어 비즈니스 로직과 연관된 작업을 수행할 수 없다.

대표적으로 인코딩 변환처리, XSS 방어, LOG, 인증등을 구현할때 사용한다.

![https://user-images.githubusercontent.com/70622731/156137692-b5923f77-787b-45a3-92b3-b554f581a2ba.png](https://user-images.githubusercontent.com/70622731/156137692-b5923f77-787b-45a3-92b3-b554f581a2ba.png)

## **인터셉터(Interceptor)**

인터셉터는 Spring이 제공하는 기술로써, 디스패처 서블릿이 컨트롤러를 호출하기 전에 요청과 응답을 참조하거나 가공할 수 있는 기능을 제공한다.

디스패처 서블릿은 핸들러 매핑을 통해 컨트롤러를 찾는데, 이때 1개 이상의 인터셉터가 등록되어 있다면 순차적으로 인터셉터들을 거쳐 컨트롤러가 실행되도록 하고, 인터셉터가 없다면 바로 컨트롤러를 실행한다.

대표적으로 인증/인가 등과 같은 공통작업, controller로 넘겨주는 정보의 가공, 로그인 처리 시 많이 사용된다.

![https://user-images.githubusercontent.com/70622731/156138871-6ea8eacf-f74d-4765-9c21-78a9f5fda9b7.png](https://user-images.githubusercontent.com/70622731/156138871-6ea8eacf-f74d-4765-9c21-78a9f5fda9b7.png)

org.springframework.web.servlet의 HandlerInterceptor 인터페이스

**preHandle**

preHandle 메소드는 컨트롤러가 호출되기 전에 실행된다. 그렇기 때문에 컨트롤러 이전에 처리해야 하는 전처리 작업이나 요청 정보를 가공하거나 추가하는 경우에 사용할 수 있다.

**postHandle**

postHandle 메소드는 컨트롤러를 호출된 후에 실행된다. 그렇기 때문에 컨트롤러 이후에 처리해야 하는 후처리 작업이 있을 때 사용할 수 있다. 이 메소드에는 컨트롤러가 반환하는 ModelAndView 타입의 정보가 제공되는데, 최근에는 Json 형태로 데이터를 제공하는 RestAPI 기반의 컨트롤러(@RestController)를 만들면서 자주 사용되지는 않는다.

**afterCompletion**

afterCompletion 메소드는 이름 그대로 모든 뷰에서 최종 결과를 생성하는 일을 포함해 모든 작업이 완료된 후에 실행된다. 요청 처리 중에 사용한 리소스를 반환할 때 사용하기에 적합하다.

![https://user-images.githubusercontent.com/70622731/156185167-31d7ef3f-dda3-4ace-8e8e-72315bf6a226.png](https://user-images.githubusercontent.com/70622731/156185167-31d7ef3f-dda3-4ace-8e8e-72315bf6a226.png)

인터셉터의 예외 흐름은 preHandle이 예외를 발생시키면 뒤에 있던 postHandle이 호출되지 않는다, 이때 주의할 점이 있는데 afterCompletion은 항상 호출이 된다는 것이다. 마치 자바의 try catch문에서 finally가 항상 작동하는 것을 생각하면 이해가 좀 더 쉽겠다

## **ViewResolver**

dispatcherServlet은 Handler Adapter에서 받아온 view 이름을 가지고 viewResolver에게 이러한 view가 있는지 물어보고 viewResolver는 view가 존재하는지 아닌지 판단하는 역할을 하게된다.

즉, ViewResolver는 사용자가 요청한 것에 대한 응답 view를 렌더링하는 역할이다.

[https://gudwnsgur.tistory.com/14](https://gudwnsgur.tistory.com/14)


---
질문

1. 스프링 동작방식
    
    1. DispatcherServlet이 브라우저로부터 요청을 받는다.
    
    2. DispatcherServlet은 요청된 URL을 __________객체에 넘기고,
    
    호출해야 할 Controller 메소드 정보를 얻는다.
    
    3. DispatcherServlet이 HandlerAdapter 객체를 가져온다.
    
    4. HandlerAdapter 객체의 메소드를 실행한다.
    
    5. Controller 객체는 비즈니스 로직을 처리하고, 그 결과를 바탕으로 뷰(ex. JSP)에 전달할 객체를 Model 객체에 저장한다. DispatcherServlet에게 view name을 리턴한다.
    
    6. DispatcherServlet은 view name을 _________에게 전달하여 View 객체를 얻는다.
    
    7. DispatcherServlet은 View 객체에 화면 표시를 의뢰한다.
    
    8. View 객체는 해당하는 뷰(ex. JSP, Thymeleaf)를 호출하며,
    
    뷰는 Model 객체에서 화면 표시에 필요한 객체를 가져와 화면 표시를 처리한다.
    


2. 스프링 컨테이너는 등록된 스프링 빈을 _____패턴으로 생성하고 관리한다. 각 메서드에 @____을 붙여 스프링 컨테이너에 스프링 빈으로 등록할 수 있다.

3. 필터와 인터셉터는 Web Spring영역에 있다. (O/X)
    
    
4. 인터셉터 인터페이스의 메소드 3가지 중에 컨트롤러가 호출된 후에 불리게 되는 2가지 메소드를 말하고, 둘의 차이를 간단하게 서술
    

