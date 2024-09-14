# Spring Boot에서 Spring AI 사용하기

이 문서는 Spring Boot 애플리케이션에 Spring AI를 통합하는 방법에 대한 개요를 제공합니다. Spring AI는 개발자가 자연어 처리, 머신러닝 통합 등을 간소화할 수 있도록 다양한 AI 모델과 상호 작용할 수 있는 기능을 제공합니다.

## 목차
- [소개](#소개)
- [사전 준비](#사전-준비)
- [Spring Boot 프로젝트에서 Spring AI 설정하기](#spring-boot-프로젝트에서-spring-ai-설정하기)
- [기본 사용법](#기본-사용법)
- [설정](#설정)
- [참고 자료](#참고-자료)

## 소개
Spring AI는 Java 애플리케이션에 AI 모델 통합을 지원하는 Spring 에코시스템의 일부입니다. Spring Boot 프로젝트에 Spring AI를 도입하면 자연어 처리, 컴퓨터 비전, 기타 머신러닝 기능을 손쉽게 활용할 수 있습니다.

## 사전 준비
- Java 17 이상
- Spring Boot 3.x 이상
- Maven 또는 Gradle을 통한 의존성 관리
- Spring Boot 및 AI/ML 기본 개념에 대한 이해

## Spring Boot 프로젝트에서 Spring AI 설정하기

1. **Spring AI 의존성 추가:**
   프로젝트의 `pom.xml` (Maven) 또는 `build.gradle` (Gradle) 파일에 필요한 Spring AI 의존성을 추가합니다.

   **Maven 사용 시:**
   ```xml
   <dependency>
       <groupId>org.springframework.ai</groupId>
       <artifactId>spring-ai-core</artifactId>
       <version>1.0.0</version>
   </dependency>
   ```

    **Gradle 사용 시:**
    ```yaml
    implementation 'org.springframework.ai:spring-ai-core:1.0.0'
   ```


### 2. Spring AI 서비스 초기화

Spring AI는 다양한 AI 작업을 위한 서비스를 제공합니다. 예를 들어, 자연어 처리(NLP) 모델을 통합하려면 해당 모델과 상호 작용하는 서비스를 생성할 수 있습니다. 

다음과 같이 Spring의 의존성 주입(Dependency Injection)을 사용하여 이러한 서비스를 설정하고 사용할 수 있습니다.

```java
import org.springframework.stereotype.Service;

@Service
public class AiService {
    
    // 의존성 주입을 통해 AI 클라이언트 설정
    private final AiClient aiClient;

    public AiService(AiClient aiClient) {
        this.aiClient = aiClient;
    }

    public String generateResponse(String prompt) {
        // AI 클라이언트를 사용하여 프롬프트에 대한 응답 생성
        return aiClient.getResponse(prompt);
    }
}

```

위와 같이 서비스 클래스를 생성한 후, 컨트롤러나 다른 서비스에서 해당 AI 서비스를 주입하여 사용할 수 있습니다.

### 3. AI 모델 구성
애플리케이션의 application.properties 또는 application.yml 파일에서 AI 모델을 구성할 수 있습니다. 

모델에 따라 API 키가 필요한 경우, 다음과 같이 설정할 수 있습니다.

application.yml 예시:

```yaml
spring:
  ai:
    model:
      name: gpt-3
      api-key: YOUR_API_KEY
      endpoint: https://api.openai.com/v1/completions
```


application.properties 예시:


``` properties
spring.ai.model.name=gpt-3
spring.ai.model.api-key=YOUR_API_KEY
spring.ai.model.endpoint=https://api.openai.com/v1/completions
```

이러한 설정을 통해 Spring AI가 사용할 모델과 API 엔드포인트 등을 지정할 수 있습니다. 중요한 정보(API 키 등)는 환경 변수나 별도의 구성 파일을 통해 관리하는 것이 좋습니다.


### 4. 애플리케이션에 AI 기능 구현

Spring AI에서 제공하는 서비스를 사용하여 애플리케이션에서 다양한 AI 작업을 수행할 수 있습니다. 

다음은 언어 모델을 활용하는 컨트롤러의 간단한 예시입니다.

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api/ai")
public class AiController {
    
    private final AiService aiService;

    @Autowired
    public AiController(AiService aiService) {
        this.aiService = aiService;
    }

    @PostMapping("/generate")
    public ResponseEntity<String> generateResponse(@RequestBody String prompt) {
        String aiResponse = aiService.generateResponse(prompt);
        return ResponseEntity.ok(aiResponse);
    }
}
```

위의 예시에서는 /api/ai/generate 엔드포인트를 통해 POST 요청으로 전달된 프롬프트에 기반한 AI 응답을 생성합니다. 

AiService는 이전 단계에서 작성한 서비스 클래스입니다.

### 기본 사용법
설정이 완료되면 애플리케이션에서 AI 모델과 상호 작용할 수 있습니다. 위의 예시에서는 POST 요청으로 전달된 프롬프트를 기반으로 AI 모델이 응답을 생성하는 엔드포인트를 만들었습니다. 

이를 확장하여 다양한 AI 작업을 수행할 수 있습니다.

#### 설정 모델 선택
> application.properties 또는 application.yml 파일을 통해 다양한 AI 모델을 선택하고 구성할 수 있습니다.

#### API 키
> AI 서비스에서 API 키가 필요한 경우, 이를 애플리케이션 프로퍼티에 안전하게 저장하고 구성해야 합니다. 민감한 정보는 환경 변수나 별도의 비밀 관리 서비스(Vault 등)를 활용하는 것이 좋습니다.

#### 커스텀 모델
> 사용자 지정 AI 모델이 있는 경우, 필요한 Spring AI 서비스를 직접 구현하여 통합할 수 있습니다.