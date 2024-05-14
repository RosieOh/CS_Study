 # 1. SpringBoot 처음 사용할 때 + Lombok 설명
 <br>

<h3>포트번호에 충돌이 생기면?</h3>
프로젝트를 반복적으로 실행하면 문제가 생길 수 있다. 이럴 경우에 아래와 같이 메세지가 발생한다.

<br>

```
*******************************
Application Failed to Start
*******************************
Description:
The Tomcat connector configured to listen on port 8080 failed to start. The port
may already be in use or the connector may be misconfigured.
​
Action:
```
<br>
해결방안 2가지가 있다.

1. application.properties 에서 server.port 를 변경한다.

2. window 경우 작업관리자 , osx 경우 ps -ef 에서 실행중인 JAVA 프로그램을 찾아 종료 후 재시작 한다.

<br>

<h3>STS에서 Tomcat을 따로 설치해야 되나?</h3>
설치할 필요가 없다. 기존의 경우 [tomcat]([) 사이트에 접속하여 tomcat.zip을 받고 이클립스나 STS에서 Server를 추가해서 실습을 진행했다. 하지만 내장된 Tomcat이 있기때문에 따로 설치는 필요없다.

<br>

<h3>@RestController 의 역할</h3>
JSP, HTML 같은 별도의 View를 제공하지 않고 문자열 데이터를 브라우저에 전송

<br>

<h3>기본 패키지가 아닌 패키지에 작성한 코드를 스프링에서 사용하고 싶다면?</h3>

@ComponentScan 을 사용하면 된다.

```
@SpringBootApplication
@ComponentScan(basePackages={"org.djlee","org.djunnni"});
public class BootApplication {
    public static void main(String[] args){
        SpringApplication.run(BootApplication.class,args);
    }
}
```

<h3>Lombok의 장점과 문제점</h3>

### 장점 :

1. 기존의 Getter, Setter , toString 에 대한걸 어노테이션으로 대체가 가능하다.

2. 코드의 간결성

3. @Data 의 장점 : Getter,Setter, equal(), hashcode(), toString() 등 파라미터없는 기본 생성자까지 자동생성 해준다.


원치 않는 속성을 출력하고 싶지 않을 때 아래와 같이 쓰면 된다.

```
@ToString(exclude={"val1"})
```

### 문제점 :
@Data를 사용할 때 주의해야 됩니다!!

@Data는 장점에서 말한 사항에 대해 묶음으로 제공하는 어노테이션이지만 ORM(Object Relation Mapping)에서 주의해야 됩니다.

ORM은 객체간 관계를 가지는 조합의 형태로, 테이블 간 연관관계를 표현합니다.

이 경우에 부모와 자식의 toString()에서 문제가 발생하는데 상호호출문제로 인하여 무한루프에 빠져 StackOverflow가 발생할 수 있습니다.

#### Test Case
```
    public class Member {
        private String id;
        private String pw;
        private School school;
​
        @Override
        public String toString() {
            return "Member [id = " +id + ",pw = "+ pw + ", school = " + school + "]";
        }
    }
    public class School {
        private String name;
        private Member member;
​
        @Override
        public String toString() {
            return "School [name = " +name + ",member = "+ member + "]";
        }
    }
```

#### 👏👏권고사항 : 라인이 길어지더라도 @Data 대신 @Getter @Setter @ToString을 따로 쓰는 이유는 여기에 있습니다.