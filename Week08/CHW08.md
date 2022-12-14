SPING의 특징 3가지 : IOC/DI,  PSA,  AOP+SOLID, (POJO)

![image](https://user-images.githubusercontent.com/87592585/196944086-92d8798f-1791-4424-9567-11b4441b0b58.png)


1. **IoC / DI (Inverse of Control / Dependency Injection)**

스프링 프레임워크에서는 여러 객체에 대한 생성 및 객체간의 의존 관계에 대한 관리를 개발자 대신 스프링이 하게 됨. 스프링 요구대로 설정만 하면 설정에 따라서 Bean(=객체)을 생성하여 컨테이너에 담고 Bean간의 의존관계를 파악하여 주입(DI)한다. ⇒ 외부(IoC 컨테이너)에서 생성된 객체를 setter() 또는 생성자를 이용하여 사용함.

(직접 객체를 생성하지 않고 xml를 사용하여 객체를 외부에서 얻어와서 호출한다. 즉, xml에서 bean을 생성한다)

DI를 통해 모듈간의 결합도가 낮아지고 유연성이 높아진다.

스프링이 모든 의존성객체를 스프링이 실행될 때 만들어주고 필요한곳에 주입시킴으로 Bean들은 싱글턴패턴의 특징을 가진다!

- **POJO** : 스프링에서 생성, 관리되며 Spring Bean이라고도 함. getter/setter로만 구성되어있으며 어떤 클래스도 상속X, 인터페이스도 구현X. EJB는 너무 무거워(복잡함을 증가시키는 lifecycle, callback 메서드들..) Spring을 사용하게 됨.

1. **AOP + SOLID**

AOP는 OOP를 보완하는 개념으로 관점지향프로그래밍이라고 부른다. 어떤 로직을 기준으로 핵심적인 관점, 부가적인 관점으로 나누어 각각의 기준들로 모듈화하겠다는 것. ex) 핵심:비즈니스로직, 부가:DB연결,파일 입출력 등등 ⇒ 중복코드줄이고 복잡도 낮추고 재사용 용이하게.

Aspect는 Advice(해야할 일), Pointcut(적용점)으로 구분됨. 스프링은 프록시 기반 AOP 지원함 = 프록시패턴 : 원래 해야할 일을 가지고 있는 객체를 감싸서 실제 클라이언트의 요청을 처리해야한다는 것

OCP: 확장하기 용이해야하며 주변 변화에 있어서는 닫혀있어야함. 변경이 발생할때마다 기본 구조를 수정해야하면 안됨. 다른 기능들을 쉽게 추가해서 사용할 수 있도록 확장에 열려있어야함. ⇒ 객체지향을 위한 가이드라인 = SOLID

1. **PSA**

서비스 추상화. @Transactional과 같이 별도 코드 없이 트랜잭션 서비스를 사용할 수 있음. 즉, 추상화 계층을 사용하여 어노테이션으로 바로 서비스를 사용할 수 있도록 해주는 것.

***** SOLID ( SRP + OCP + LSP + ISP + DIP )**

시스템에 새로운 기능이 확장되거나 변경사항이 있는 경우 기존 기능들이 영향을 적게 받아야함.

1. **SRP : 단일 책임원칙**

= 객체는 단 하나의 책임만 가질 수 있다. = 객체 간 응집도는 높고 결합도가 낮은 프로그램.

1. **OCP : 개방폐쇄원칙**

기존코드변경하지않고 확장할 수 있어야함. Spring Container가 이 역할을 한다. 다형성과는 다름.

1. **LSP : 리스코프 치환원칙**

부모클래스를 상속하는 자식클래스는 부모클래스의 기능을 무시하거나 오버라이딩을 자제해야한다.

1. **ISP : 인터페이스 분리의 원칙**

여러 구체적인 인터페이스로 나눠주는 것이 객체지향관점에서 더 좋은 설계이다.

1. **DIP : 의존관계 역전원칙**

스프링에서는 DI, DI container로 자바 객체의 의존성을 연동해준다.

---

*Q1) DI 방법 3가지는 무엇인가요?*

A1) 

- Setter Injection : getter/setter메서드의 setter메서드로 객체주입. 낮은 결합도. 단, 객체 주입안해도 사용이 가능하여 NullPointException 주의할것
- Constructor Injection : 생성자에 @Autowired 선언. 사용하기 좋은 이유는 필수적으로 사용해야하는 의존성 없이는 Instance 만들지 못하도록 강제할 수 있음. final 사용가능
- Field Injection : 변수 선언부에 @Autowired 선언. 단, 이 경우 의존성을 주입하기가 쉬워진다. 생성자의 parameter가 많아지고 하나의 class가 많은 책임을 떠안게 됨. 단일책임(SRP)원칙 위반.

*Q2) Bean들이 싱클턴패턴의 특징을 가지는 이유는 무엇인가요?*

A2) Spring에서는 Bean들을 Spring Container에서 생성되는데 모두 싱글턴으로 관리됨

*Q3) 스프링에서 DB에 접근하여 실제 데이터를 조회/조작하는 클래스(DAO 역할)는 무엇인가요?*

A3) Mapper

More Questions :

[https://mangkyu.tistory.com/95](https://mangkyu.tistory.com/95)

[https://dev-coco.tistory.com/163](https://dev-coco.tistory.com/163)
