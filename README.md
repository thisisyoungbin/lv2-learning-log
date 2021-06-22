# 우아한 테크코스 레벨2 학습로그

# 스프링 체스 

## Spring MVC

- 스프링 프레임 워크를 활용해 서버와 웹이 통신한다.
- @GetMapping, @PostMapping 등 어노테이션을 통해 해당 요청에 응답할 수 있다.
- @ComponentScan, @Component(@Controller, @Service, @Repository) 등의 어노테이션으로 스프링 빈으로 등록 가능하다.
- [학습 테스트](https://github.com/next-step/spring-learning-test/tree/mvc)

## 태그

- Spring Framework, Spring MVC, Web Programming


## Spring JDBC

- Spring JDBCtemplate을 활용해 데이터베이스와 연결할 수 있다.
- [학습 테스트](https://github.com/next-step/spring-learning-test/tree/jdbc)

## 태그

- Spring Framework, Spring Core, Web Programming


## Spring Core

- IoC(제어의 역전) : 프레임워크(스프링)이 객체의 생성과 관리를 담당한다.
- DI(의존성 주입) : 의존성을 주입하는 방식에는 생성자 주입, 필드 주입, setter 주입 방식이 있고 주로 생성자 주입 방식을 사용한다. [링크](https://madplay.github.io/post/why-constructor-injection-is-better-than-field-injection)
- [학습 테스트](https://github.com/next-step/spring-learning-test/tree/core)

## 태그

- Spring Framework, Spring Core, Web Programming


## Http Method

- GET(조회), POST(생성), PUT, DELETE(삭제) 등 상황에 따라 다른 메서드를 사용한다.
- 이번 미션에서는 GET, POST, DELETE 메서드를 사용했다.
- [HTTP 요청 메서드](https://developer.mozilla.org/ko/docs/Web/HTTP/Methods)

## 태그

- Http Method, REST API, Web Programming


## ResponseEntity

- Http 응답에 해당하는 헤더와 바디를 가진 객체
- 상태코드와 헤더를 설정할 수 있다.
- [ResponseEntity란?](https://devlog-wjdrbs96.tistory.com/182)

## 태그

- Web Programming, REST API

## HTTP 응답 코드

- 200 : 요청이 처리됐음을 나타내는 응답 코드
- 201 : 요청에 처리됐고, 자원이 생성됐음을 나타내는 응답 코드
- 302 : 요청을 처리하고 Location 헤더에 주어진 주소로 리다이렉트 한다.
- [HTTP 상태 코드](https://developer.mozilla.org/ko/docs/Web/HTTP/Status)

## 태그

- HTTP 상태 코드, REST API, Web Programming


***

# 배포, 인프라

## 배스쳔 호스트(Bastion Host)

- 침입 차단 소프트웨어가 설치되어 내부와 외부 네트워크 사이에서 일종의 게이트 역할을 수행하는 호스트
- 가상 서버의 설치, 인증, 로그 등을 담당한다.
- 서비스 정상 트래픽과 관리자용 트래픽을 구분할 수 있다.

## 태그

Bastion, 운영, 보안



## 프록시

- 프록시란? : 서버와 클라이언트 사이에 중계기로 클라이언트 대신 서버와 대리로 통신을 수행하는 것  
- 프록시 서버의 역할
  - 클라이언트 대신 서버에게 요청을 받아 응답한다.
  - 캐시를 통해 자원들을 저장할 수 있다.
  - 프록시 서버를 거치는 요청 및 응답을 확인할 수 있다.
  - 프록시 서버로 넘어온 데이터를 조작할 수 있다.
- 캐시(Cache) : 메모리 영역으로 데이터를 가져와 접근하는 방식.
  - 네트워크 비용을 감소시킬 수 있다.
  - 응답 속도를 향상 시킬 수 있다.
- 필터 : 프록시 서버를 거치는 요청 및 응답을 확인할 수 있다.
  - 보안성을 향상 시킬 수 있다.
  - 프록시를 통한 모든 요청/응답을 로깅할 수 있다.
- TransCoder :  프록시 서버로 넘어온 데이터를 조작할 수 있다.
  - 데이터 압축, 언어 변환 등
- 익명화 : HTTP 메시지에서 신원을 특정할 수 있는 정보를 제거해 개인 정보 보호 및 익명성을 보장한다.



### 포워드 프록시 

- 클라이언트와 인터넷 사이에 위치해 클라이언트 대신 서버에 요청을 보내는 역할
- 트래픽 제어 및 부적절한 콘텐츠 제어



### 리버스 프록시

- 서버와 인터넷 사이에 위치해서 서버의 응답을 대신 클라이언트에게 전달해주는 역할
- 웹 서버의 보안 기능, 캐싱을 통한 성능 개선이 가능하다. 
- 로드 밸런싱 역할을 할 수 있다.

## 태그

네트워크, 운영 

***


# 지하철 노선도 관리

## @Controller vs @RestController

- @Controller : 전통적인 Spring MVC의 컨트롤러, 반환 값이 String인 경우 뷰 이름으로 인식되어 해당 문자와 일치하는 뷰를 찾고, 뷰를 렌더링 한다.
- @RestController : Restful 웹서비스의 컨트롤러, 반환 값으로 뷰를 찾는 것이 아니라, HTTP 메시지 바디에 바로 입력한다. 애노테이션을 확인해보면 @ResponseBody가 추가되어 있다.
- HTTP Response Body가 생성되는 방식에 차이가 있다.
- @Controller는 주로 View를 반환하기 위해 사용. 데이터를 반환하기 위해 @ResponseBody 애노테이션을 추가로 사용해야한다.
- @RestController : 쉽게 생각해서 @Controller + @ResponseBody. Json 형태로 데이터를 반환한다.

## 태그

- Spring Annotation, Spring MVC


## 스프링 애노테이션을 이용한 예외처리

- @ExceptionHandler : @Controller, @RestController가 적용된 Bean 내에서 발생하는 예외를 잡아서 해당 애노테이션이 붙은 하나의 메서드에서 처리해준다. @ExceptionHandler를 등록한 @(Rest)Controller 에만 적용된다.
- @(Rest)ControllerAdvice : 모든 @(Rest)Controller에서(전역) 발생할 수 있는 예외를 잡아 처리해준다. 하나의 클래스 단위로 작성하며, 클래스 내의 @ExceptionHandler 애노테이션을 등록한 메서드를 통해 각 예외들을 처리할 수 있다.
- ExceptionResponse 사용시 사용자에게 내부 구현 코드(클래스명 등)을 노출시키면 안 된다.
- HTTP 상태코드를 반환할 땐, 서버의 기준으로 던진다. 잘못된 입력이 들어온 경우 BAD_REQUEST, 리소스가 없는 경우 NOT_FOUND 등등..

## 태그

- Spring Annotation, Spring MVC, 예외처리


## ATDD vs 통합테스트

- ATDD : 시나리오를 받고 거기에 맞춰 개발하는 방식. `시나리오의 정상 작동여부`를 목적으로 테스트한다. 
- 통합테스트 : 개발자 관점에서 `각 기능이 유기적으로 연결되어 정상작동 하는지`를 목적으로 테스트한다.
- 통합테스트가 시나리오 기반으로 작성됐다면? 통합테스트이자 인수테스트이다.

## 태그

- ATDD, 통합테스트
- 참고 : [웨지의 정리](https://woowacourse.slack.com/archives/C01KBN5K1HC/p1621485675053100)


## Request 유효성 검증

- @Valid : 파라미터에 전달되는 Request 앞에 해당 애노테이션을 등록해 Request 객체의 필드 값을 검증한다.
- `implementation ‘org.springframeworkd.boot:spring-boot-starter-validation’` 의존성 추가를 통해 사용할 수 있다.
- Request의 필드에 @NotNull, @NotEmpty, @NotBlank 등을 붙여 유효성을 검증한다.
- @NotNull : null만 허용하지 않음(“ “, “” 허용)
- @NotEmpty: null, “” 둘 다 허용하지 않음(“ “ 허용)
- @NotBlank: null, “”, “ “ 모두 허용하지 않음
- 그 외에 @Size, @Min, @Max, @Email 등의 애노테이션을 통해 유효성을 검증할 수 있다.

## 태그

- Spring Annotation, Spring Framework
- 참고 : [@NotNull, @NotEmpty, @NotBlank 의 차이점](https://sanghye.tistory.com/36)


## 인터페이스 DI

- Dao를 추상화해야 하는 이유? : 익숙하게 사용하던 JDBC가 아닌 다른 라이브러리를 사용하게 된다면? 의존성 주입을 받는 부분에서 모두 영향을 받게 된다. 따라서 Dao를 만들 땐 추상화 된 Repository 인터페이스를 구현해서 만들자.

## 태그

- Spring DI, @Repository, OOP


## Controller, Service, Repository 의 책임

- Controller : 요청에 대해 응답한다. 어떤 로직도 수행하지 않는다.
- Service : 요청에 대한 적절한 응답을 만든다. 주요 로직을 수행하나, 될 수 있으면 도메인을 통해 실행할 수 있는지 고민해보자
- Repository : 어떤 로직도 갖고 있지 않으며 전달받은 데이터를 C.R.U.D 한다.

## 태그

- Spring MVC
- 참고 : [Controller, Service, Repository](https://m.blog.naver.com/jysaa5/221751719334)


## 제네릭

- 클래스 내부에서 사용할 데이터 타입을 외부에서 지정하는 기법
- 테스트 코드에서 StationRequest, LineRequest를 받고 있던 파라미터를 제네릭을 사용해 중복 제거

## 태그

- JDK

## 로그 남기기

- slf4j 라이브러리를 활용해 간단하게 로그를 남길 수 있다.

- 로그 레벨

  - TRACE -> DEBUG -> INFO -> WARN -> ERROR
    - 개발 서버는 DEBUG 출력
    - 운영 서버는 INFO 출력

- 로그 레벨 설정법(application.properties)

  ```
  #wootech.hello 패키지와 그 하위 로그 레벨 설정 
  logging.level.wootech.hello=debug
  ```

- 로그를 남길 때 `log.debug("info = " + info)` 와 같이 남기는 경우 불필요한 문자 연산이 추가된다. 따라서 `log.debug("info = {}", info)` 식으로 남기도록 한다.

## 태그

- slf4j, Logger, LoggerFactory


***


# 지하철 경로 조회

# 학습로그


## JWT(JSON Web Token)

JWT 토큰은 토큰에 대한 기본정보와 전달할 정보(유저 정보)와 signature를 포함한다.
웹 서버의 경우 HTTP 헤더에 넣어서 전달한다.
JWT의 구조 : {헤더}.{내용(payload)}.{서명}

- 헤더 : 토큰의 타입과 해싱 알고리즘의 정보를 담고 있다.
- 내용 : 토큰에 담을 정보가 들어있다. 여기(페이로드)에 담기는 정보의 한 조각을 '클레임'이라고 한다.
  - 클레임 : name/value의 한쌍으로 이뤄져있고, 토큰에는 여러 개의 클레임을 넣을 수 있다.
  - 클레임의 종류는 크게 세 분류로 되어있다.
    1. 등록된 클레임
    2. 공개 클레임
    3. 비공개 클레임
  - 등록된 클레임 : 토큰에 대한 정보를 담기위해 이미 정해진 클레임. 사용은 선택적이다.
    - iss : 토큰 발급자(issuer)
    - sub : 토큰 제목(subject)
    - aud : 토큰 대상자(audience)
    - exp: 토큰 만료시간(expiration), NumericDate 형식
    - nbf : Not Before 토큰의 활성 날짜와 비슷한 개념으로 해당 날짜가 지나기 전까지는 토큰이 처리되지 않는다.
    - iat : 토큰 발급 시간(issued at)
    - jti : JWT의 고유 식별자. 주로 중복적인 처리를 방지하기 위해 사용된다.
  - 공개 클레임 : 충돌 방지를 위해 클레임 이름을 URI 형식으로 짓는다.
  - 비공개 클레임 :  보통 서버와 클라이언트의 협의하에 사용되는 클레임. 중복될 수 있으니 유의해야 한다.
- 서명 : 헤더의 인코딩 값과, 정보의 인코딩 값을 합쳐 주어진 비밀키로 해싱해 생성한다.


## 태그

JWT
참고 : [JWT 소개 및 구조](https://velopert.com/2389)



## 트랜잭션(@Transactional)

트랜잭션이란? : DB상태를 변환시키는 하나의 논리적 기능을 수행하기 위한 작업의 단위 혹은 연산

- 트랜잭션의 성질 : 원자성, 격리성, 일관성, 지속성
- 트랜잭션 전파 : 트랜잭션을 시작하거나, 기존 트랜잭션에 참여하는 방법을 결정하는 속성
  - REQUIRED : 디폴트 속성. 하나의 트랜잭션이 시작된 후 다른 트랜잭션 경계가 설정된 메소드를 호출하면 자연스럽게 같은 트랜잭션으로 묶인다.
- 트랜잭션 격리 수준 : 여러 트랜잭션이 진행될 때 트랜잭션의 작업 결과를 여타 트랜잭션에게 어떻게 노출할 것인지를 결정하는 기준
  - DEFAULT : DB의 격리수준을 따르는 게 일반적이며 대부분 READ_COMMITTED
  - READ_COMMITTED : 트랜잭션이 커밋하지 않은 정보는 읽을 수 없다. 하나의 트랜잭션이 읽은 로우를 다른 트랜잭션이 수정 가능하다.
  - SERIALIZABLE : 트랜잭션을 순차적으로 진행시키기 때문에, 여러 트랜잭션이 동시에 같은 테이블의 정보를 액세스 할 수 없다. 낮은 성능.
- 트랜잭션 제한시간(timeout) : 트랜잭션에 제한시간을 지정할 수 있다.
- 읽기전용 트랜잭션(readOnly) : 트랜잭션을 읽기 전용으로 설정한다. 해당 트랜잭션 작업 안에는 쓰기 작업이 없다는 것을 명시적으로 나타낸다.
- 스프링에서 메서드 별로 다른 Transactional 속성을 줄 수 있다.

## 태그

Spring Annotation, @Transactional
참고 : [트랜잭션이란 무엇인가?](https://coding-factory.tistory.com/226), [트랜잭션 속성](https://springsource.tistory.com/136)



## 인증과 인가

- **인증이란?** : (식별 가능한 정보로) 서비스에 등록된 유저의 신원을 입증하는 과정이다.
  - 인증하기 : base64 인코더를 이용해 인코딩을 하고 Request Header를 통해 전달한다.
  - DB에서 체크 후 유효한 값인 경우 ok.
  - 매번 인증해야 하는 번거로움이 발생 -> 브라우저의 스토리지를 이용한다.



- **인가란?** : 인증된 사용자에 대한 자원 접근 권한 확인
  - Oauth : 다른 웹사이트 상의 자신들의 정보에 대해 접근 권한을 부여할 수 있는 공통적인 수단(개방형 표준이다)
  - Oauth의 역할 구성 - Resourse Owner(유저) - Client(서비스) - Resource Server(Oauth 제공자)

- 장점 
  - 사용자 - 서비스에 ID/PW를 알려주지 않아도 된다. 원할 때 액세스 토큰의 권한 취소가 가능하다. 
  - 서비스 - 유저의 액세스 토큰만 가지고 있으면 된다. 사용자의 ID/PW를 몰라도 허가 받은 API에 접근 가능하다.


## 태그

인증과 인가, Oauth

참고 : [10분 테코톡 - 루피의 인증과 인가](https://www.youtube.com/watch?v=JZgD8aPkHSc&t=35s&ab_channel=%EC%9A%B0%EC%95%84%ED%95%9CTech), 


***


# 스프링 협업 미션

# 학습로그


## 백엔드 유효성 검증의 필요성

아이디나 비밀번호와 같이 회원 정보를 입력 받을 때, 프론트에서 값 검증을 하기 때문에 ''서버쪽에서 검증을 또 해줄 필요가 있을까?' 하고 생각했었다. 

- 실제 데이터를 저장시키는 행위를 하는 곳은 백엔드다. 따라서 저장된 값에 대한 책임 또한 백엔드에 있다. 
- 프론트에만 유효성 검사를 맡기는 것은 내가 수행해야 할 책임을 프론트에 전가하는 것이다.

## 태그

참고 : [프론트에서만 하는 유효성 검사가 문제인 이유](https://jojoldu.tistory.com/157#recentComments)



## 스프링 인터셉터

- 스프링에서 인터셉터의 의미는 중간에 요청을 가로채서 어떠한 일을 한다는 것이다.
- 클라이언트의 요청이 컨트롤러에 가기 전에 가로채고, 응답이 클라이언트에게 가기전에 가로챈다. 즉, 인터셉터는 **DispatcherServlet**이 컨트롤러를 요청하기 전. 후에 요청과 응답을 가로채서 가공할 수 있도록 한다.

- 인터셉터 사용법
  - HandlerInterceptorAdaptor 클래스를 상속받는다. HandlerInterceptorAdaptor를 상속받으면 `preHandle()`, `postHandle()`, `afterHandle()` 메서드를 사용할 수 있다.
    - `preHandler()` : 클라이언트에서 컨트롤러로 요청이 갈 때 요청을 가로채고 가공한다.
    - `postHandler()` : 컨트롤러에서 클라이언트로 응답할 때 응답을 가로채고 가공한다.
    - `afterCompletion()` : 컨트롤러에서의 요청, 응답 처리와 화면처리까지 모두 끝나면 실행되는 메서드.
  - 각 메서드의 반환값이 true이면 핸들러의 다음 체인이 실행되지만 false이면 중단하고 남은 인터셉터와 컨트롤러가 실행되지 않는다.

## 태그

참고 : [스프링 인터셉터 설정](https://to-dy.tistory.com/21)



## CORS(Cross-Origin Resource Sharing)

- CORS ? : 다른 출처의 자원을 공유하는 것

- 추가 HTTP 헤더를 사용하여 다른 출처의 선택한 자원에 접근할 수 있는 권한을 부여하도록 브라우저에 알려주는 체제이다.

- 출처(origin) - URL의 Protocol, Host, Port를 통해 같은 출처인지 다른 출처인지 판단한다.

- CORS 접근제어 시나리오

  - 단순 요청(SImple Request)

    - Preflight 요청 없이 바로 요청을 날린다.
      - GET, POST, HEAD 메서드여야 한다.
      - Content-Type은 다음 중 하나여야 하낟.
        - application/x-www-form-urlencoded
        - multipart/form-data
        - text/plain
      - 헤더는 Accept, Accept-Language, Content-Language, Content-Type만 허용된다.

  - 프리플라이트 요청

    - HTTP OPTIONS 메서드를 통해 다른 도메인의 리소스에 요청이 가능한 지 확인한다.

    - 요청이 가능하다면 실제 요청을 보낸다.

      ```
      PREFLIGHT REQUEST
      
      Origin: 요청 출처
      Access-Control-Request-Method: 실제 요청의 메서드
      Access-Control-Request-Headers: 실제 요청의 추가 헤더
      ```

      ```
      PREFLIGHT RESPONSE
      
      Access-Control-Allow-Origin: 서버 측 허가 출처
      Access-Control-Allow-Methods: 서버 측 허가 메서드
      Access-Control-Allow-Header: 서버 측 허가 헤더
      Access-Control-Allow-Max-Age: Preflight 응답 캐시 기간
      ```

  - 인증정보 포함 요청

    - 인증 관련 헤더를 포함할 때 사용하는 요청
    - 클라이언트측 - credentials : include
    - 서버측 - Access-Control-Allow-Credentials : true

- CORS 에러 해결하는 방법

  - 프론트 프록시 서버 설정
  - 직접 헤더에 설정
  - 스프링 부트 이용

## 태그

CORS

출처 : [10분 테코톡 - 나봄의 CORS](https://www.youtube.com/watch?v=1grtWKqTn50&ab_channel=%EC%9A%B0%EC%95%84%ED%95%9CTech%EC%9A%B0%EC%95%84%ED%95%9CTech)





