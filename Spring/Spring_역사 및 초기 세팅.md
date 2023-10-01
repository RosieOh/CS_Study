# 01. Spring Framework 개요

<br>

## 01-01. Spring 역사
- EJB를 주 프레임워크로 사용할 때 불편했던 점들(무거움, 따라야 할 스펙들이 복잡함)을 해소하기 위해 탄생함
- 2002년 로드존슨이 출판한 도서 Expert One-on-One J2EE Design and Development에 선보인 코드가 현재 Spring의 근간이 됨
- 이 도서를 읽은 개발자들이 '코드가 책으로만 존재하기에는 너무 아깝다'라며 로드 존슨의 허가를 받은 뒤 프레임워크로 발전시킴
- 2003년 6월 Apache 2.0 License로 공개됨
- 2004년에 1.0v이 배포됨

<br>

## 01-02. Spring Framework란?
- 자바, 엔터프라이즈 개발, 오픈소스, light-weigth "애플리케이션 프레임워크"이다.
- 특정 계층이나 기술, 업무 분야에 국한되지 않고 애플리케이션의 전 영역을 포괄하는 범용적인 프레임워크를 말함.
- 굉장히 범용적이고 다양한 분야에서 활용하고 있지만, 모두 다 알아야 활용할 수 있는 것은 아닌 만큼 기본에 충실해서 학습해야 합니다.

### 1) 경량급 프레임워크
- 단순한 웹 컨테이너에서도 엔터프라이즈 개발의 고급기술을 대부분 사용할 수 있습니다.
- EJB에 비해 경량급입니다. 또한 일반 자바 객체만을 사용하여 엔터프라이즈급의 고급 기술을 구현할 수 있습니다.

### 2) 엔터프라이즈 개발 용이
- 개발자가 복잡하고 실수하기 쉬운 Low Level에 많이 신경 쓰지 않으면서 Business Logic 개발에 전념할 수 있도록 해줍니다.

### 3) 오픈소스
- Spring은 OpenSource 로서 누구나 사용할 수 있습니다. 다만, 아무나 잘 하는 것은 아니며, 무료 프레임워크의 단점을 극복하고, 장점을 극대화하여 사용하여하여 합니다.

<br>


## 01-03. Spring Framework 특징
### 1) 컨테이너 제공
- Spring 컨테이너(Container)는 Java 객체의 Life Cycle을 관리하며, Spring 컨테이너(Container)로부터 필요한 객체를 가져와 사용할 수 있습니다.

### 2) DI(Dependency Injection) 지원
- Spring은 설정 파일이나 어노테이션(Annotation)을 통해서 객체 간의 의존관계를 설정할 수 있도록 하고 있습니다.

### 3) AOP(Aspect Oriented Programming) 지원
- Spring은 트랜잭션(Transaction)이나 로깅(Logging), 보안(Security)과 같이 공통적으로 필요로 하는 모듈들을 실제 핵심 모듈에서 분리해서 적용할 수 있습니다.

### 4) POJO(Plain Old Java Object) 지원
- Sring 컨테이너(Container)에 저장되는 Java객체는 특정한 인터페이스(Interface)를 구현하거나, 특정 클래스(Class)를 상속받지 않아도 됩니다.

### 5) 트랜잭션(Transaction) 처리를 위한 일관된 방법을 지원
- JDBC(Java DataBase Connectivity), JTA(Java Transaction API) 등 어떤 트랜잭션을 사용하더라도 설정(Configuration)을 통해 정보를 관리하므로 트랜잭션 구현에 상관없이 동일한 코드를 사용할 수 있습니다.

### 6) 영속성(Persistence)과 관련된 다양한 API 지원
- Spring은 Mybatis, Hibernate 등 데이터베이스 처리를 위한 ORM(Object Relational Mapping) 프레임워크들과의 연동 지원합니다.

<br>

## 01-04. Spring Framework 주요 모듈 구성

![Spring Framework 주요 모듈 구성](./springframework001.png)

### 1) Data Access/Integration(데이터 접근 및 통합)

JDBC(Java DataBase Connectivity) : Java 기반 애플리케이션의 데이터를 데이터베이스에 저장 및 업데이트하거나, 데이터베이스에 저장된 데이터를 Java에서 사용할 수 있도록 하는 자바 API입니다.

ORM(Object Relational Mpping) : 객체와 관계형 데이터베이스의 데이터를 자동으로 매핑(연결)해주는 것을 말합니다.

OXM(Object-XML Mapping) : XML과 자바(Java) 오브젝트를 매핑해서 상호 변환해주는 기술입니다.

JMS(Java Message Service) : 사람이 아닌 애플리케이션의 구성 요소가 소비하는 요청, 보고서, 이벤트로 메시지를 작성, 전송 수신 및 읽을 수 있는 메시징 서비스를 제공하는 것을 말합니다.

Transactions : 데이터베이스에서 여러 요청이 한 꺼번에 처리가 되어야 하는 트랜잭션(Transaction)이 정의되고, 구현될 수 있도록 어노테이션으로 제공합니다.

<br>

### 2) Web
- Websocket :  HTTP 통신의 단점인 단방향 통신을 개선하기 위하여 웹 소켓을 활용하여 반 영구적인 양방향 통신을 제공합니다.
- Servlet : MVC 처리 패턴에서 Controller에 해당하는 요청에 대한 처리 작업이 진행되도록 합니다.
- Web : JSP(Java Server Page)에 속하는 Expression, Directive, Declaration, Expression Language, Java Standard Tag Library 등을 활용할 수 있는 웹 모듈을 제공합니다.
- Portlet : 포털 페이지를 구성하는 웹 컴포넌트(Web Component)를 제공하며, 또한, MVC 처리 패턴에서 View 속하는 곳에 데이터를 처리하여 보내 질 수 있는 역할을 수행합니다.

<br>

### 3) Core Container
- 주요한 객체들(Bean)을 관리해주는 아주 중요한 모듈
- Beans : 스프링 컨테이너에 의해 관리되는 재사용 가능한 소프트웨어 컴포넌트로서 하나의 클래스로 부터 얻어진 객체이며, 주입(Inject)의 대상입니다. XML의 bean 태그나 @Configuration 어노테이션으로 설정되는 주입 설정 클래스에서 @Bean 어노테이션으로 설정됩니다.
- Core : 스프링 프레임워크의 근간이 되는 요소로 IoC(Invert Of Control) 또는 DI(Dependency Injection)기능을 지원하는 요소입니다.
- Context : 여러 Bean을 관련있는 요소로 각 각 분리하여 하나의 XML 파일로 구성될 수 있도록 하는 요소입니다.
- SpEL : Spring Expresion Language의 약자로 런타임(실행) 시 객체 그래프 쿼리 및 조작을 지원하는 표현 언어로서 #{표현식} 이나 ${표현식} 으로된 파라미터나 연산식, 비교식 등을 구현할 수 있도록 돕습니다.

### 4) Test
- JUnit 및 Spring Test 를 지원합니다.
- JUnit은 @Test, @Ignore, @Before, @After, @BeforeClass, @AfterClass 등의 어노테이션을 활용한 assert 메서드로 단위 테스트 프레임을 구성을 지원합니다.
- Spring Test는 @RunWith, @ContextConfiguration, @Autowired 어노테이션을 활용하여 별도의 컨텍스트 없이도 테스트 케이스를 작성할 수 있도록 지원합니다.

### 5) Spring Object
- AOP(Aspect-Oriented Programming) : 공통적으로 적용이 되어야 하는 부분이 여러 군데에 흩어져 있을 경우 사용시기(Jointpoint)가 되었을 경우 대비해 여러 사용시기(Jointpoint)를 정규 표현식인 포인트컷(Pointcut)으로 만들어 각 각의 대상 클래스에 있는 코드를 연결하여 하나의 객체로 만드는데 이를 위빙(Weaving)이라 하고, 위빙(Weaving) 된 것을 동작되도록 합니다. 이 때 위빙(Weaving)된 동작을 어드바이스(Advice)라고 합니다.
- Aspects : 보통 AspectJ에 의한 관점지향 프로그래밍을 의미하며, Spring AOP는 공통적인 문제를 해결하기 위해 간단히 구현하고, Spring Container에 의해 관리되는 Bean에만 적용하지만, Aspects는 Spring AOP보다 강력하고, 완전체를 별도로 구성하여 진행하기 때문에 많이 복잡해집니다.
- Instrumentation : 빈의 생명주기와 설정 그리고 처리방법을 관리하는 스프링 컨테이너입니다.
- Messaging : 시스템의 구성 요소 간에 메시징을 지원하고 관리하는 요소입니다.

<br>

## 01-05. Spring Framework 의 개발환경 설정

### 1) Open JDK 설치

https://www.azul.com/downloads/?package=jdk#zulu


위 사이트에 접속하여 Open JDK 17 버전의 Windows
x86 64-bit용으로 다운로드 받은 후 설치합니다.

![OpenJDK 17 설치](./capture/setting00_01.png)



### 2) 인텔리제이 설치

https://www.jetbrains.com/ko-kr/idea/download/?section=windows

위 사이트에 접속하여 인텔리 제이를 다운로드 받아 설치합니다.

![인텔리제이 설치](./capture/setting00_02.png)


### 3) 인텔리제이 프로젝트 생성

#### 3-1) 새로운 프로젝트 생성

![인텔리제이 새로운 프로젝트 생성](./capture/setting01.png)


#### 3-2) 새로운 프로젝트 설정

![인텔리제이 새로운 프로젝트 생성 및 설정](./capture/setting02.png)


#### 3-3) 새로운 프로젝트 라이브러리 로딩 설정

![인텔리제이 새로운 프로젝트 생성](./capture/setting03.png)


![인텔리제이 새로운 프로젝트 설정](./capture/setting04.png)

#### 3-4) D:\kim\springStudy\study1\pom.xml 기본 설정

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>kr.co.study</groupId>
  <artifactId>study</artifactId>
  <packaging>war</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>study Maven Webapp</name>
  <url>http://maven.apache.org</url>
  <properties>
    <java-version>17</java-version>
    <org.springframework-version>5.3.20</org.springframework-version>
    <org.aspectj-version>1.9.0</org.aspectj-version>
    <org.slf4j-version>2.0.0</org.slf4j-version>
  </properties>
  <dependencies>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-context</artifactId>
      <version>${org.springframework-version}</version>
      <exclusions>
        <exclusion>
          <groupId>commons-logging</groupId>
          <artifactId>commons-logging</artifactId>
        </exclusion>
      </exclusions>
    </dependency>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-webmvc</artifactId>
      <version>${org.springframework-version}</version>
    </dependency>

    <dependency>
      <groupId>org.aspectj</groupId>
      <artifactId>aspectjrt</artifactId>
      <version>1.9.0</version>
    </dependency>

     </dependencies>
  <build>
    <finalName>study1</finalName>
    <plugins>
      <plugin>
        <artifactId>maven-eclipse-plugin</artifactId>
        <version>2.9</version>
        <configuration>
          <additionalProjectnatures>
            <projectnature>org.springframework.ide.eclipse.core.springnature</projectnature>
          </additionalProjectnatures>
          <additionalBuildcommands>
            <buildcommand>org.springframework.ide.eclipse.core.springbuilder</buildcommand>
          </additionalBuildcommands>
          <downloadSources>true</downloadSources>
          <downloadJavadocs>true</downloadJavadocs>
        </configuration>
      </plugin>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>2.5.1</version>
        <configuration>
          <source>17</source>
          <target>17</target>
          <compilerArgument>-Xlint:all</compilerArgument>
          <showWarnings>true</showWarnings>
          <showDeprecation>true</showDeprecation>
        </configuration>
      </plugin>
      <plugin>
        <groupId>org.codehaus.mojo</groupId>
        <artifactId>exec-maven-plugin</artifactId>
        <version>1.2.1</version>
        <configuration>
          <mainClass>org.test.int1.Main</mainClass>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```

#### 3-5) 톰캣 서버 다운로드

![인텔리제이 새로운 프로젝트 설정](./capture/setting05.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting06.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting07.png)



#### 3-5) 톰캣 서버 설정 및 실행

![인텔리제이 새로운 프로젝트 설정](./capture/setting08.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_1.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_2.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_3.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_4.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_5.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_6.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_7.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_8.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_9.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_10.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_11.png)

![인텔리제이 새로운 프로젝트 설정](./capture/setting08_12.png)


<br><br>

# 02. Spring Framework 설정

## 02-1. 의존성 설정

D:\kim\springStudy\study2\pom.xml 설정

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>org.study2</groupId>
  <artifactId>study2</artifactId>
  <packaging>war</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>study2 Maven Webapp</name>
  <url>http://maven.apache.org</url>
  <properties>
    <java-version>17</java-version>
    <org.springframework-version>5.3.20</org.springframework-version>
    <org.slf4j-version>2.0.0</org.slf4j-version>
  </properties>
  <dependencies>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-context</artifactId>
      <version>${org.springframework-version}</version>
      <exclusions>
        <exclusion>
          <groupId>commons-logging</groupId>
          <artifactId>commons-logging</artifactId>
        </exclusion>
      </exclusions>
    </dependency>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-webmvc</artifactId>
      <version>${org.springframework-version}</version>
    </dependency>
    <dependency>
      <groupId>org.aspectj</groupId>
      <artifactId>aspectjrt</artifactId>
      <version>1.9.0</version>
    </dependency>

    <!-- slf4j and log4j -->
    <dependency>
      <groupId>org.slf4j</groupId>
      <artifactId>slf4j-api</artifactId>
      <version>${org.slf4j-version}</version>
    </dependency>
    <dependency>
      <groupId>org.slf4j</groupId>
      <artifactId>jcl-over-slf4j</artifactId>
      <version>${org.slf4j-version}</version>
      <scope>runtime</scope>
    </dependency>
    <dependency>
      <groupId>org.slf4j</groupId>
      <artifactId>slf4j-log4j12</artifactId>
      <version>${org.slf4j-version}</version>
      <scope>runtime</scope>
    </dependency>
    <dependency>
      <groupId>log4j</groupId>
      <artifactId>log4j</artifactId>
      <version>1.2.15</version>
      <exclusions>
        <exclusion>
          <groupId>javax.mail</groupId>
          <artifactId>mail</artifactId>
        </exclusion>
        <exclusion>
          <groupId>javax.jms</groupId>
          <artifactId>jms</artifactId>
        </exclusion>
        <exclusion>
          <groupId>com.sun.jdmk</groupId>
          <artifactId>jmxtools</artifactId>
        </exclusion>
        <exclusion>
          <groupId>com.sun.jmx</groupId>
          <artifactId>jmxri</artifactId>
        </exclusion>
      </exclusions>
      <scope>runtime</scope>
    </dependency>

    <!-- 의존성 주입 라이브러리 - @Inject -->
    <dependency>
      <groupId>javax.inject</groupId>
      <artifactId>javax.inject</artifactId>
      <version>1</version>
    </dependency>

    <!-- 서블릿(servlet-api 2.5, jsp-api 2.1, jstl 1.2) -->
    <dependency>
      <groupId>javax.servlet</groupId>
      <artifactId>servlet-api</artifactId>
      <version>2.5</version>
      <scope>provided</scope>
    </dependency>
    <dependency>
      <groupId>javax.servlet.jsp</groupId>
      <artifactId>jsp-api</artifactId>
      <version>2.1</version>
      <scope>provided</scope>
    </dependency>
    <dependency>
      <groupId>javax.servlet</groupId>
      <artifactId>jstl</artifactId>
      <version>1.2</version>
    </dependency>

    <!-- 테스트 도구(junit 4.13, spring-test 5.3.20)   -->
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.13</version>
      <scope>test</scope>
    </dependency>
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-test</artifactId>
      <version>${org.springframework-version}</version>
    </dependency>

    <!-- maven build tool(3.2.1) -->
    <dependency>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-archetype-plugin</artifactId>
      <version>3.2.1</version>
    </dependency>

    <!-- lombok(1.18.22)-->
    <dependency>
      <groupId>org.projectlombok</groupId>
      <artifactId>lombok</artifactId>
      <version>1.18.22</version>
    </dependency>

    <!-- DB 로그(log4jdbc-log4j2 1.16) -->
    <dependency>
      <groupId>org.bgee.log4jdbc-log4j2</groupId>
      <artifactId>log4jdbc-log4j2</artifactId>
      <version>1.16</version>
    </dependency>

    <!-- 스프링 jdbc(5.3.20)-->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-jdbc</artifactId>
      <version>${org.springframework-version}</version>
    </dependency>

    <!-- DBMS Common Library(1.4) -->
    <dependency>
      <groupId>commons-dbcp</groupId>
      <artifactId>commons-dbcp</artifactId>
      <version>1.4</version>
    </dependency>

    <!-- 마리아DB 연결 라이브러리(3.1.4) -->
    <dependency>
      <groupId>org.mariadb.jdbc</groupId>
      <artifactId>mariadb-java-client</artifactId>
      <version>3.1.4</version>
    </dependency>

    <!-- 스프링 트랜잭션 도구(5.3.20) -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-tx</artifactId>
      <version>${org.springframework-version}</version>
    </dependency>

    <!-- mybatis 라이브러리 - mybatis 3.4.0 -->
    <dependency>
      <groupId>org.mybatis</groupId>
      <artifactId>mybatis</artifactId>
      <version>3.4.0</version>
    </dependency>

    <!-- mybatis-spring 1.3.2 -->
    <dependency>
      <groupId>org.mybatis</groupId>
      <artifactId>mybatis-spring</artifactId>
      <version>1.3.2</version>
    </dependency>

    <!-- 구글 JSON : gson 2.7 -->
    <dependency>
      <groupId>com.google.code.gson</groupId>
      <artifactId>gson</artifactId>
      <version>2.7</version>
    </dependency>

    <!-- 웹 크롤링 도구 jsoup 1.12.1 -->
    <dependency>
      <groupId>org.jsoup</groupId>
      <artifactId>jsoup</artifactId>
      <version>1.12.1</version>
    </dependency>

    <!-- 범용 json(20200518) -->
    <dependency>
      <groupId>org.json</groupId>
      <artifactId>json</artifactId>
      <version>20200518</version>
    </dependency>

    <!-- 심플 json(0.4) -->
    <dependency>
      <groupId>org.apache.clerezza.ext</groupId>
      <artifactId>org.json.simple</artifactId>
      <version>0.4</version>
    </dependency>

    <!-- jackson library(json to xml) 2.9.4-->
    <dependency>
      <groupId>com.fasterxml.jackson.core</groupId>
      <artifactId>jackson-databind</artifactId>
      <version>2.9.4</version>
    </dependency>

    <!-- jackson mapper(1.9.13) -->
    <dependency>
      <groupId>org.codehaus.jackson</groupId>
      <artifactId>jackson-mapper-asl</artifactId>
      <version>1.9.13</version>
    </dependency>

    <!-- 스프링 암호화 라이브러리 -->
    <dependency>
      <groupId>org.springframework.security</groupId>
      <artifactId>spring-security-core</artifactId>
      <version>5.4.0</version>
    </dependency>
    <dependency>
      <groupId>org.springframework.security</groupId>
      <artifactId>spring-security-web</artifactId>
      <version>5.4.0</version>
    </dependency>
    <dependency>
      <groupId>org.springframework.security</groupId>
      <artifactId>spring-security-config</artifactId>
      <version>5.4.0</version>
    </dependency>

    <!-- 파일 첨부 및 업로드 라이브러리 commons-fileupload 1.3.2, commons-io 2.4  -->
    <dependency>
      <groupId>commons-fileupload</groupId>
      <artifactId>commons-fileupload</artifactId>
      <version>1.3.2</version>
    </dependency>
    <dependency>
      <groupId>commons-io</groupId>
      <artifactId>commons-io</artifactId>
      <version>2.4</version>
    </dependency>

    <!--  이미지 편집 라이브러리 imgscalr-lib 4.0 -->
    <dependency>
      <groupId>org.imgscalr</groupId>
      <artifactId>imgscalr-lib</artifactId>
      <version>4.0</version>
    </dependency>

    <!-- 자바 이메일 기본 라이브러리 javax.mail-api 1.4.7 -->
    <dependency>
      <groupId>javax.mail</groupId>
      <artifactId>javax.mail-api</artifactId>
      <version>1.4.7</version>
    </dependency>

    <!-- 이메일 및 자원에 대한 외부 송출 라이브러리 spring-context-support 스프링mvc 버전과 동일 -->
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-context-support</artifactId>
      <version>${org.springframework-version}</version>
    </dependency>

    <!-- java의 validation 라이브러리 validation-api 2.0.1.Final -->
    <dependency>
      <groupId>javax.validation</groupId>
      <artifactId>validation-api</artifactId>
      <version>2.0.1.Final</version>
    </dependency>

    <!-- 폼 검증을 애노테이션으로 검증하는 라이브러리 hibernate-annotations 3.5.6-Final -->
    <dependency>
      <groupId>org.hibernate</groupId>
      <artifactId>hibernate-annotations</artifactId>
      <version>3.5.6-Final</version>
    </dependency>

    <!-- hibernate Validator 라이브러리 hibernate-validator 6.0.8.Final, jaxb-api 2.3.0 -->
    <dependency>
      <groupId>org.hibernate.validator</groupId>
      <artifactId>hibernate-validator</artifactId>
      <version>6.0.8.Final</version>
    </dependency>
    <dependency>
      <groupId>javax.xml.bind</groupId>
      <artifactId>jaxb-api</artifactId>
      <version>2.3.0</version>
    </dependency>
    <dependency>
      <groupId>org.junit.jupiter</groupId>
      <artifactId>junit-jupiter</artifactId>
      <version>RELEASE</version>
      <scope>compile</scope>
    </dependency>

    <!-- 애노테이션 설정 api 추가 -->
    <dependency>
      <groupId>javax.annotation</groupId>
      <artifactId>javax.annotation-api</artifactId>
      <version>1.3.2</version>
    </dependency>

    <!-- 음력 달력 -->
    <dependency>
      <groupId>com.ibm.icu</groupId>
      <artifactId>icu4j</artifactId>
      <version>4.0.1</version>
    </dependency>

  </dependencies>
  <build>
    <finalName>study2</finalName>
    <plugins>
      <plugin>
        <artifactId>maven-eclipse-plugin</artifactId>
        <version>2.9</version>
        <configuration>
          <additionalProjectnatures>
            <projectnature>org.springframework.ide.eclipse.core.springnature</projectnature>
          </additionalProjectnatures>
          <additionalBuildcommands>
            <buildcommand>org.springframework.ide.eclipse.core.springbuilder</buildcommand>
          </additionalBuildcommands>
          <downloadSources>true</downloadSources>
          <downloadJavadocs>true</downloadJavadocs>
        </configuration>
      </plugin>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>2.5.1</version>
        <configuration>
          <source>17</source>
          <target>17</target>
          <compilerArgument>-Xlint:all</compilerArgument>
          <showWarnings>true</showWarnings>
          <showDeprecation>true</showDeprecation>
        </configuration>
      </plugin>
      <plugin>
        <groupId>org.codehaus.mojo</groupId>
        <artifactId>exec-maven-plugin</artifactId>
        <version>1.2.1</version>
        <configuration>
          <mainClass>org.test.int1.Main</mainClass>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```

## 02-2. 웹 설정

D:\kim\springStudy\study2\src\main\webapp\WEB-INF\web.xml 의 설정

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app version="2.5" xmlns="http://java.sun.com/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://java.sun.com/xml/ns/javaee https://java.sun.com/xml/ns/javaee/web-app_2_5.xsd">
  <display-name>Study2 Web Application</display-name>

  <!-- 빈 설정 파일 등록 : applicationContext.xml 지정 -->
  <context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>/WEB-INF/applicationContext.xml</param-value>
  </context-param>

  <!-- 모든 서블릿과 필터가 공유하는 Context Spring 컨테이너 생성 -->
  <listener>
    <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
  </listener>

  <!-- 내부 웹 관련 처리 작업 설정 파일 등록 : dispatcher-servlet.xml 지정 -->
  <!-- 암호화 처리 설정 파일 등록 : spring-security.xml 지정 -->
  <servlet>
    <servlet-name>appServlet</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    <init-param>
      <param-name>contextConfigLocation</param-name>
      <param-value>
        /WEB-INF/dispatcher-servlet.xml
        /WEB-INF/spring-security.xml
      </param-value>
    </init-param>
    <load-on-startup>1</load-on-startup>
  </servlet>

  <servlet-mapping>
    <servlet-name>appServlet</servlet-name>
    <url-pattern>/</url-pattern>
  </servlet-mapping>

  <!-- 한글 깨짐 방지 -->
  <filter>
    <filter-name>encodingFilter</filter-name>
    <filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
    <init-param>
      <param-name>encoding</param-name>
      <param-value>UTF-8</param-value>
    </init-param>
  </filter>
  <filter-mapping>
    <filter-name>encodingFilter</filter-name>
    <url-pattern>/*</url-pattern>
  </filter-mapping>
</web-app>
```

<br><br>

## 02-3. 애플리케이션 빈 등록 및 설정

D:\kim\springStudy\study2\src\main\webapp\WEB-INF\applicationContext.xml

### 1) applicationContext.xml 생성

- D:\kim\springStudy\study2\src\main\webapp\WEB-INF 디렉토리에서 마우스 오른쪽 버튼 을 누르고 나오는 메뉴에서 [New]-[File] 을 선택하고, 입력 란에 applicationContext.xml을 입력하고, Enter를 칩니다.

![applicationContext.xml 파일 추가](./capture/setting09.png)

![applicationContext.xml 파일 추가](./capture/setting09_1.png)


<br>


### 2) applicationContext.xml 작성

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:mybatis-spring="http://mybatis.org/schema/mybatis-spring"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xmlns:jdbc="http://www.springframework.org/schema/jdbc"
       xmlns:tx="http://www.springframework.org/schema/tx"
       xsi:schemaLocation="http://www.springframework.org/schema/jdbc http://www.springframework.org/schema/jdbc/spring-jdbc-4.3.xsd
		http://mybatis.org/schema/mybatis-spring http://mybatis.org/schema/mybatis-spring-1.2.xsd
		http://www.springframework.org/schema/beans https://www.springframework.org/schema/beans/spring-beans.xsd
		http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-4.3.xsd
		http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-4.3.xsd
		http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-4.3.xsd">

<!-- applicationContext : 빈을 설정하는 파일로 외부 자원과 연동하는 부분을 설정 -->

    <!-- 데이터베이스 설정 -->
    <!-- spring-jdbc-5.3.20.jar 안의 드라이버매니저 연결 -->
    <bean id="dataSource" class="org.springframework.jdbc.datasource.SimpleDriverDataSource">
        <property name="driverClass" value="org.mariadb.jdbc.Driver"/>
        <property name="url" value="jdbc:mariadb://localhost:3306/haebeop"/>
        <property name="username" value="root"/>
        <property name="password" value="1234"/>
    </bean>

    <!-- sql을 대신할 my-batis 설정 : mybatis-spring-1.3.2.jar의 세션팩토리빈클래스 연결 -->
    <bean id="sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">
        <property name="dataSource" ref="dataSource"/>
        <property name="configLocation" value="classpath:/mybatis-config.xml"/>
        <property name="mapperLocations" value="classpath*:/mappers/**/*Mapper.xml"/>
    </bean>

    <!-- SqlSession 객체 주입 -->
    <bean id="sqlSession" class="org.mybatis.spring.SqlSessionTemplate" destroy-method="clearCache">
        <constructor-arg name="sqlSessionFactory" ref="sqlSessionFactory"/>
    </bean>

    <!-- 트랜잭션 및 DB 패키지 방안 및 각 종 로깅과 보안 설정 -->
    <bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
        <property name="dataSource" ref="dataSource"/>
    </bean>

    <context:annotation-config/>

    <!-- @Transactional 어노테이션 처리 -->
    <tx:annotation-driven transaction-manager="transactionManager"/>


</beans>
```

<br>

## 02-4. 맵퍼 등록 및 설정

### 1) mybatis-config.xml 파일 생성

D:\kim\springStudy\study2\src\main\resources 디렉토리에서 마우스 오른쪽 버튼 을 누르고 나오는 메뉴에서 [New]-[File] 을 선택하고, 입력 란에 mybatis-config.xml을 입력하고, Enter를 칩니다.

![mybatis-config.xml 파일 추가](./capture/setting09_2.png)

![mybatis-config.xml 파일 생성](./capture/setting09_3.png)


<br>


### 2) mybatis-config.xml 파일 작성

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE configuration PUBLIC
        "-//mybatis.org//DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>
    <typeAliases>
        <package name="kr.ed.haebeop" />
    </typeAliases>
</configuration>
```

<br>

### 3) mappers 디렉토리 생성 및 파일 작성

- D:\kim\springStudy\study2\src\main\resources 디렉토리에서 마우스 오른쪽 버튼 을 누르고 나오는 메뉴에서 [New]-[Directory] 를 선택하고, 입력 란에 mappers을 입력하고, Enter를 칩니다.

![mappers 디렉토리 생성](./capture/setting09_4.png)

![mappers 디렉토리 생성](./capture/setting09_5.png)

- D:\kim\springStudy\study2\src\main\resources\mappers 디렉토리에서 마우스 오른쪽 버튼 을 누르고 나오는 메뉴에서 [New]-[Directory] 를 선택하고, 입력 란에 testMapper.xml을 입력하고, Enter를 칩니다.

![testMapper.xml 파일 생성](./capture/setting09_51.png)

![testMapper.xml 파일 생성](./capture/setting09_6.png)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper
        PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
<mapper namespace="test">
    <select id="testSelectList" resultType="kr.ed.haebeop.domain.test">
        select * from test
    </select>
</mapper>
```

<br><br>

## 02-5. 서블릿 등록 및 설정

### 1) 서블릿 디스패처 작성 - dispatcher-servlet.xml 작성

- D:\kim\springStudy\study2\src\main\webapp\WEB-INF 디렉토리에서 마우스 오른쪽 버튼 을 누르고 나오는 메뉴에서 [New]-[File] 를 선택하고, 입력 란에 dispatcher-servlet.xml을 입력하고, Enter를 칩니다.

![dispatcher-servlet.xml 파일 생성](./capture/setting10.png)

![dispatcher-servlet.xml 파일 생성](./capture/setting10_1.png)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans:beans xmlns="http://www.springframework.org/schema/mvc"
             xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
             xmlns:beans="http://www.springframework.org/schema/beans"
             xmlns:context="http://www.springframework.org/schema/context"
             xsi:schemaLocation="http://www.springframework.org/schema/mvc https://www.springframework.org/schema/mvc/spring-mvc.xsd
		http://www.springframework.org/schema/beans https://www.springframework.org/schema/beans/spring-beans.xsd
		http://www.springframework.org/schema/context https://www.springframework.org/schema/context/spring-context.xsd">

    <!-- dispatcher-servlet.xml : 내부 웹 접근 및 처리 작업 설정 파일 -->

    <!--  접근 자원에 대한 권한 설정 -->
    <resources mapping="/resources/**" location="/resources/" />
    <resources mapping="/data/**" location="/data/" />
    <resources mapping="/admin/**" location="/WEB-INF/views/admin" />
    <resources mapping="/board/**" location="/WEB-INF/views/board" />
    <resources mapping="/check/**" location="/WEB-INF/views/check" />
    <resources mapping="/guestbook/**" location="/WEB-INF/views/guestbook" />
    <resources mapping="/free/**" location="/WEB-INF/views/free" />
    <resources mapping="/include/**" location="/WEB-INF/views/include" />
    <resources mapping="/member/**" location="/WEB-INF/views/member" />
    <resources mapping="/notice/**" location="/WEB-INF/views/notice" />
    <resources mapping="/qna/**" location="/WEB-INF/views/qna" />
    <resources mapping="/reservation/**" location="/WEB-INF/views/reservation" />
    <resources mapping="/util/**" location="/WEB-INF/views/util" />
    <resources mapping="/sample/**" location="/WEB-INF/views/sample" />
    <resources mapping="/sample2/**" location="/WEB-INF/views/sample2" />
    <resources mapping="/test/**" location="/WEB-INF/views/test" />
    <resources mapping="/error/**" location="/WEB-INF/views/error" />

    <!-- 컨트롤러에서 던진 URL : /notice/noticeList -->
    <!-- 실제 존재하는 URL : /WEB-INF/views/notice/noticeList.jsp -->
    <!-- 앞(prefix)의 /WEB-INF/views, 뒤(suffix)의 .jsp  -->
    <!-- 리졸버에 대한 접두사와 접미사 설정 -->
    <beans:bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
        <beans:property name="prefix" value="/WEB-INF/views" />
        <beans:property name="suffix" value=".jsp" />
    </beans:bean>

    <!-- 멀티파트 리졸버 설정 -->
    <beans:bean id="multipartResolver" class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
        <beans:property name="defaultEncoding" value="UTF-8"/> <!-- 기본 인코딩 -->
        <beans:property name="maxUploadSize" value="52428800"/> <!-- 파일 사이즈 : 50MB -->
        <beans:property name="maxInMemorySize" value="1048576"/> <!-- 메모리 사이즈 : 1MB -->
    </beans:bean>

    <!-- 멀티파트 업로드 디렉토리 지정 -->
    <beans:bean id="uploadPath" class="java.lang.String">
        <beans:constructor-arg value="D:\kim\springStudy\study2\src\main\webapp\resources\upload" />
    </beans:bean>

    <!-- 기본 메인 패키지 및 컨트롤러 패키지 설정 -->
    <context:component-scan base-package="kr.ed.haebeop.controller" />
    <annotation-driven />


    <!-- 인터셉터 : 글쓰기와 같은 회원권한을 가진 경우는 반드시 로그인 페이지를 거쳐서 시도할 것  -->
    <!-- <beans:bean id="sampleIntercepter" class="kr.co.teaspoon.util.SampleInterceptor" />
    <beans:bean id="adminIntercepter" class="kr.co.teaspoon.util.AdminInterceptor" />
    <interceptors>
        <interceptor>
            <mapping path="/free/**"/>
            <beans:ref bean="sampleIntercepter" />
        </interceptor>
        <interceptor>
            <mapping path="/admin/**"/>
            <beans:ref bean="adminIntercepter" />
        </interceptor>
    </interceptors> -->
    <!-- free 디렉토리의 view(.jsp)를 접근하려면 SampleInterceptor 클래스에
    제시한 조건이 맞으면 접근 가능하게 할 수 있도록 함 -->
    <!-- admin 디렉토리의 view(.jsp)를 접근하려면 AdminInterceptor 클래스에
    제시한 조건이 맞으면 접근 가능하게 할 수 있도록 함 -->
</beans:beans>
```

<br>

### 2) 서블릿 피스패처에서 설정한 접근 자원에 대한 디렉토리 생성

- D:\kim\springStudy\study2\src\main\webapp\WEB-INF 디렉토리에서 마우스 오른쪽 버튼 을 누르고 나오는 메뉴에서 [New]-[Directory] 를 선택하고, 입력 란에 views를 입력하고, Enter를 칩니다.

- D:\kim\springStudy\study2\src\main\webapp\WEB-INF\views 디렉토리에서 마우스 오른쪽 버튼 을 누르고 나오는 메뉴에서 [New]-[Directory] 를 선택하고, 입력 란에 admin를 입력하고, Enter를 칩니다.

- 위와 같이 views 디렉토리 안에 board, check, guestbook, free, qna, include, member, notice, reservation, util, test, error 디렉토리를 생성합니다.

- D:\kim\springStudy\study2\src\main\webapp 디렉토리에서 마우스 오른쪽 버튼을 누르고 나오는 메뉴에서 [New]-[Directory] 를 선택하고, 입력 란에 resource를 입력하고, Enter를 칩니다.

- 위와 같이 webapp 디렉토리 안에 data 디렉토리를 생성합니다.


![dispatcher-servlet.xml 파일 생성](./capture/setting10_2.png)


<br><br>

## 02-6. 로그 출력 및 백업 설정

### 1) log4j.xml 생성 및 작성

- D:\kim\springStudy\study2\src\main\resources 디렉토리에서 마우스 오른쪽 버튼을 누르고 나오는 메뉴에서 [New]-[File] 를 선택하고, 입력 란에 log4j.xml을 입력하고, Enter를 칩니다.

![log4j.xml 작성](./capture/setting11.png)

![log4j.xml 작성](./capture/setting11_1.png)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE log4j:configuration PUBLIC "-//APACHE//DTD LOG4J 1.2//EN" "log4j.dtd">
<log4j:configuration>
    <!-- Appenders -->
    <appender name="console" class="org.apache.log4j.ConsoleAppender">
        <param name="Target" value="System.out" />
        <layout class="org.apache.log4j.PatternLayout">
            <param name="ConversionPattern" value="%-5p: %c - %m%n" />
        </layout>
    </appender>

    <logger name="kr.ed.haebeop.controller">
        <level value="info" />
    </logger>

    <logger name="kr.ed.haebeop.domain">
        <level value="info" />
    </logger>

    <logger name="kr.ed.haebeop.persistence">
        <level value="info" />
    </logger>

    <logger name="kr.ed.haebeop.repository">
        <level value="info" />
    </logger>

    <logger name="kr.ed.haebeop.service">
        <level value="info" />
    </logger>

    <logger name="kr.ed.haebeop.util">
        <level value="info" />
    </logger>

    <logger name="kr.ed.haebeop.test">
        <level value="info" />
    </logger>

    <logger name="kr.ed.haebeop">
        <level value="info" />
    </logger>

    <logger name="org.springframework.core">
        <level value="info" />
    </logger>
    <logger name="org.springframework.beans">
        <level value="info" />
    </logger>
    <logger name="org.springframework.context">
        <level value="info" />
    </logger>
    <logger name="org.springframework.web">
        <level value="info" />
    </logger>

    <root>
        <priority value="warn"/>
        <appender-ref ref="console"/>
    </root>
</log4j:configuration>
```

<br>

### 2) 관련 패키지 생성

- D:\kim\springStudy\study2\src\main 디렉토리에서 마우스 오른쪽 버튼을 누르고 나오는 메뉴에서 [New]-[Directory] 를 선택하고, 입력 란에 java를 입력하고, Enter를 칩니다.

- D:\kim\springStudy\study2\src\main\java 디렉토리에서 마우스 오른쪽 버튼을 누르고 나오는 메뉴에서 [New]-[Package] 를 선택하여 아래 그림과 같이 log4j.xml에서 지정한 패키지를 생성합니다.

![관련 패키지 작성](./capture/setting11_2.png)

<br>

### 3) 로그 백업 파일 작성 - logback.xml 작성

- D:\kim\springStudy\study2\src\main\resources 디렉토리에서 마우스 오른쪽 버튼을 누르고 나오는 메뉴에서 [New]-[File] 를 선택하고, 입력 란에 logback.xml을 입력하고, Enter를 칩니다.

![logback.xml 작성](./capture/setting12.png)

![logback.xml 작성](./capture/setting12_1.png)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <logger name="jdbc.sqlonly" level="DEBUG" />
    <logger name="jdbc.sqltiming" level="INFO" />
    <logger name="jdbc.audit" level="WARN" />
    <logger name="jdbc.resultset" level="ERROR" />
    <logger name="jdbc.resultsettable" level="ERROR" />
    <logger name="jdbc.connection" level="INFO" />

    <appender name="CONSOLE" class="ch.qos.logback.core.ConsoleAppender">
        <layout class="ch.qos.logback.classic.PatternLayout">
            <pattern>%d{HH:mm:ss.SSS} [%thread] %-4level [%logger.%method:%line]-
                %msg%n</pattern>
        </layout>
    </appender>

    <appender name="LOGFILE"
              class="ch.qos.logback.core.rolling.RollingFileAppender">
        <file>/WEB-INF/logback.log</file>
        <rollingPolicy class="ch.qos.logback.core.rolling.TimeBasedRollingPolicy">
            <fileNamePattern>logback.%d{yyyy-MM-dd}.log</fileNamePattern>
            <!-- 30일 지난 파일은 삭제한다. -->
            <maxHistory>30</maxHistory>
        </rollingPolicy>
        <encoder>
            <pattern>%d{yyyy-MM-dd HH:mm:ss.SSS} %-4level [%logger.%method:%line]
                - %msg %n</pattern>
        </encoder>
    </appender>

    <!-- 로그의 레벨( 지정된 로그 레벨 이상만 수집 ) : DEBUG < INFO < WARN < ERROR < FATAL -->
    <logger name="myweb" additivity="false">
        <level value="INFO" />
        <appender-ref ref="LOGFILE" />
        <appender-ref ref="CONSOLE" />
    </logger>

    <root>
        <level value="INFO" />
        <appender-ref ref="CONSOLE" />
    </root>
</configuration>
```

<br>

### 4) 데이터베이스 로그 파일 작성 - log4jdbc.log4j2.properties 작성

- D:\kim\springStudy\study2\src\main\resources 디렉토리에서 마우스 오른쪽 버튼을 누르고 나오는 메뉴에서 [New]-[File] 를 선택하고, 입력 란에 log4jdbc.log4j2.properties를 입력하고, Enter를 칩니다.

![log4jdbc.log4j2.properties 작성](./capture/setting13.png)

![log4jdbc.log4j2.properties 작성](./capture/setting13_1.png)

```properties
log4jdbc.spylogdelegator.name=net.sf.log4jdbc.log.slf4j.Slf4jSpyLogDelegator
```

<br><br>

## 02-7. 암호화 라이브러리 연결 - spring-security.xml 파일 작성

- D:\kim\springStudy\study2\src\main\webapp\WEB-INF 디렉토리에서 마우스 오른쪽 버튼을 누르고 나오는 메뉴에서 [New]-[File] 를 선택하고, 입력 란에 spring-security.xml을 입력하고, Enter를 칩니다.

![spring-security.xml 파일 작성](./capture/setting14.png)

![spring-security.xml 파일 작성](./capture/setting14_1.png)


## 02-8. 데이터베이스 설정 

- 마리아DB 의 GUI 도구인 HeidiSQL을 실행하고, 접속한 후 아래 그림과 같이 데이터베이스를 생성하고, 테스트용 테이블을 작성한 후 더미 데이터를 입력합니다.

```sql
CREATE DATABASE haebeop;

USE haebeop;

CREATE TABLE test(num INT AUTO_INCREMENT PRIMARY KEY,
title VARCHAR(100) NOT NULL);

INSERT INTO test VALUES (DEFAULT, '테스트제목1');
INSERT INTO test VALUES (DEFAULT, '테스트제목2');
INSERT INTO test VALUES (DEFAULT, '테스트제목3');
INSERT INTO test VALUES (DEFAULT, '테스트제목4');
INSERT INTO test VALUES (DEFAULT, '테스트제목5');

SELECT * from test;
```

<br><br>

## 02-9. 도메인(dto) 생성

- D:\kim\springStudy\study2\src\main\java\kr\ed\haebeop\domain 패키지 디렉토리에서 마우스 오른쪽 버튼을 누르고 나오는 메뉴에서 [New]-[Java Class] 를 선택하고, 입력 란에 Test를 입력하고, Enter를 칩니다.

![Test 클래스 작성](./capture/setting15.png)

![Test 클래스 작성](./capture/setting15_1.png)

```java
package kr.ed.heabeop.domain;

import lombok.AllArgsConstructor;
import lombok.Data;
import lombok.NoArgsConstructor;

@Data
@NoArgsConstructor
@AllArgsConstructor
public class Test {
    private int num;
    private String title;
}
```


