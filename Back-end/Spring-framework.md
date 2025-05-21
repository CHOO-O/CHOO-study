# 스프링 프레임워크(Spring Framework)

### 개요

**Java** 기반의 오픈소스 프레임워크이다.<br>

엔터프라이즈급 애플리케이션 개발을 단순화하고 구조화하기 위해 설계되었다.<br>

### 핵심 특징

#### POJO(Plain Old Java Object) 기반 개발

특별한 규칙이나 상속 없이, **일반적인 자바 객체(POJO)** 만으로 개발할 수 있도록 설계되었다.<br>
따라서 개발자는 자유롭고 편하게 코드를 작성할 수 있다.<br>

#### 제어의 역전(Inversion of Control, IoC)

개발자가 프로그램의 흐름을 직접 제어하는 것이 아니라, 프레임워크가 전체 흐름을 제어하고, 필요한 시점에 개발자의 코드를 호출한다.<br>

#### 의존성 주입(Dependency Injection, DI)

IoC의 대표적인 구현 방법 중 하나로, **객체 간의 의존 관계를 외부에서 주입**해주는 설계 패턴이다.<br>
개발자가 직접 필요한 객체를 생성하거나 연결하지 않고, 스프링이 대신 주입해준다.<br>

```
// 예시

@Component // 스프링이 이 클래스를 관리하게 한다.
public class OrderRepository {
    public void save(String item) {
        System.out.println("주문 저장: " + item);
    }
}

@Component // 스프링이 이 클래스를 관리하게 한다.
public class OrderService {
    ...
    @Autowired // 필요한 객체를 스프링이 자동으로 주입하게 한다.
    public OrderService(OrderRepository orderRepository) {
        /*
          여기서 new OrderRepository()처럼 직접 객체를 만들지 않았음에도 사용할 수 있는 이유는,
          스프링이 OrderRepository 객체를 대신 생성해서 이 자리에 넣어주기 때문이다.
        */
        this.orderRepository = orderRepository;
    }
    ...
}
```

#### 관점 지향 프로그래밍(Aspect-Oriented Programming, AOP)

어떠한 기능에 대해 <br>

1. **핵심 기능** : 애플리케이션의 핵심 기능
2. **부가 기능** : 반복되어 사용되는 추가적인 기능

이라는 두 가지 **관점**에 따라 깔끔하게 분리하여 관리하는 프로그래밍 방식이다.<br>

로깅, 트랜잭션 관리, 보안, 캐싱 등에 사용할 수 있다.<br>

```
// 예시 : 로깅

@Aspect // 이 클래스가 공통 기능을 정의함을 나타낸다.
@Component
public class LogAspect {

    @Before("execution(* com.example.service.*.*(..))")
    /*
      @Before Advice로 메서드 실행 전 logBefore()를 실행하도록 한다.
      com.example.service 패키지 내의 모든 메서드에 적용한다.
    */
    public void logBefore() {
        System.out.println("메서드 실행 전 로그 출력!");
    }
}

```

### 장점

🔹 **객체 지향적인 설계** : 객체 간의 의존 관계를 느슨하게 만들어 유지보수가 쉽고 유연하다.

🔹 **모듈화된 구조** : 필요한 기능만 선택해서 사용할 수 있어, 프로젝트에 맞는 유연한 구성이 가능하다.

🔹 **풍부한 기능과 생태계** : 웹, 데이터 접근, 보안, 메시징 등 다양한 기능을 통합적으로 제공하며, Spring Boot, Spring Security 등 확장 프로젝트도 풍부하다.

🔹 **테스트 용이성** : DI 구조 덕분에 단위 테스트와 모킹(mock)이 쉬워지고, 테스트 지원 모듈도 제공된다.

🔹 **기업에서 검증된 안정성** : 많은 대규모 서비스와 기업 시스템에서 사용되어 안정성이 검증되어 있다.

### 단점

🔹 **복잡한 설정** : XML 또는 Java 기반 설정이 많고, 프로젝트를 처음 구성할 때 손이 많이 간다.

🔹 **높은 진입 장벽** : 학습하는 데 다소 시간이 필요하다.

이러한 단점을 보완하고 더 쉽게 스프링을 사용할 수 있도록 등장한 것이 🔗 [Spring Boot](https://github.com/CHOO-O/CHOO-study/blob/main/Back-end/Spring-boot.md) 이다.
