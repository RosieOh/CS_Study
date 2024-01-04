# Spring Boot 최종 정리

> <h3>Spring Boot 기본 제공 | 3.1.6 기준</h3>
- web
- test
- jdbc
- security(activation)
- RESTful api/JSON
- data-jpa
- cache - 캐싱을 통해 용량을 간소화

> dependencies {<br/>
&nbsp;  &nbsp;  &nbsp; implementation 'org.springframework.boot:spring-boot-starter-web'<br/>
&nbsp;  &nbsp;  &nbsp; providedRuntime 'org.springframework.boot:spring-boot-starter-tomcat'<br/>
&nbsp;  &nbsp;  &nbsp; testImplementation 'org.springframework.boot:spring-boot-starter-test'<br/>
}
- 기본적으로 위 3개가 설정됨

> <h3>/resources.static/index.html</h3>
- 기본 메인 페이지
- 특별하게 경로 지정을 안했을 경우 static에 넣는다 
- Tomcat이 내장되어 있기 때문에 가능하다. - 서버가 자동으로 동작하기 때문에 Spring "Boot"

> <h3>Server</h3> 
- dispatcher-servlet
- @SpringBootApplication 안에 dispatcher-servlet 내장
- <p>2023-11-24T14:33:42.766+09:00  INFO 15400 --- [nio-8086-exec-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring DispatcherServlet 'dispatcherServlet'</p>

## Spring boot Running Process(스프링 부트 처리 흐름)
> <h3>Client = Web Browser</h3>
- Server => Dispatcher
- 서버에 자바 기본엔진을 전달하는 역할
- Dispatcher => Controller

> <h3>Controller</h3>
- HandlerMapping(@GetMapping(URL)) => URL Mapping =>
- 호출된 URL Mapping의 하단부의 해당 메소드 => 서비스 로직 호출 =>
- Reposiotory(Mapper) 호출 => DTO로 결과 반환 =>
- 반환된 정보(DTO)를 Model에 넣기 => View로 포워딩

## Spring Boot MVC Architecture(스프링 부트 MVC 구조)
> <h3>프레젠테이션 계층(Presentation Layer) => Controller / View</h3>
- Controller -> View Resolver -> View
  - View(Jsp, Thymeleaf, Mustache~)
- RestController -> MessageConverter -> http(JSON 응답)

> <h3>비즈니스 계층(Business Layer) => Service(비즈니스 로직 계층)</h3>

> <h3>데이터 접근 계층(Data Access Layer) => Repository(Persistance : 영속 계층)</h3>
- Mybatis : DTO(멤버가 테이블과 일치) / VO(멤버가 실제(물리) 테이블과 불일치)
- Data JPA : DTO(View)/Entity(실제 테이블과 같은 객체 - Table Mapping)
  - DTO(View) - Controller로 가는 역할
  - Entity(실제 테이블과 같은 객체 - Table Mapping) - Repository로 가는 역할
  - @Builder가 DTO, Entity의 역할을 진행


> Datatable.js를 사용할 경우 SQL은 1번만 사용

> 예상 면접 질문 : 자바의 디자인패턴이 무엇인가요?
> 
> 자바 프로그래밍 디자인 패턴
- GoF(Gang of Four) 패턴 : 에릭 감마, 리차드 헬름, 랄프 존슨, 존 블라시디스이가 모여 자바의 프로그래밍 기법을 구체화 하고, 체계화 한 패턴
- 생성(Creational) 패턴 : 객체를 효율적으로 생성하기 위한 패턴
  - 생성자
    - Abstract Factory
    - Factory Method
    - Build
    - prototype
    - Singleton
- 구조(Structural) 패턴 : 하나 이상의 클래스나 인터페이스를 혼합하여 더 큰 구조로 만들어 주는 패턴
  - 필드
    - Facade
    - Adapter
    - Composite
    - Proxy
    - Bridge
    - Decorator
    - Flyweight
- 행위(Behavioral) 패턴 : 객체가 가지는 메소드를 합치거나 분리하기 위한 패턴
  - 메소드
    - Observer
    - Strategy
    - State
    - Memento
    - Iterator
    - Command,...
