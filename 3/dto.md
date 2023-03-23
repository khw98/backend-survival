# DTO

**-data transfer object란?**

메소드 호출 횟수를 줄이기 위해 호출에 대해 필요한 모든 데이터를 가지는, 데이터 전송을 위한 객체이다

(자바로 치면 get\~, set\~ 의 모음집 같은 느낌)

DTO를 이용하여 단일 호출로 여러 매개변수를 한번에 처리하여 호출 횟수를 줄이고 캡슐화를 통해 민감한 정보를 숨길 수 있다



프로세스 간 통신(IPC) : 말 그대로 프로세스 간 데이터 전송을 위한 통신에   대한 방식, 경로에 관한 것

여기서 프로세스 = 메모리에  load된프로그램

매개체로는 주로 파일, 소켓, 메모리 등이 쓰이며 주된 방식으로는

* 공유 메모리 : 통신할 프로세스 간에 공유 가능한 메모리 영역을 만들어서 사용
* PIPE : 파일 시스템에 임시 공간을 만들고 이곳을 통해 프로세스 간 데이터 교환이 이뤄짐, 단방향으로 read / write 용 파이프를 별도로 만들어야 한다
* 소켓 :  port 가지고 네트워크 소켓 통신으로 데이터 교환, 원격 프로세스 간 통신에서 사용됨
* 원격 프로시저 호출(RPC) : 별도의 원격제어 위한 코드 없이 다른 주소 공간에서 함수나 프로시저를 실행할 수 있게 함 -> 다른 위치 프로세스의 메소드도 호출해서 사용할 수 있게 한다

자바의 경우 원격 함수 호출을 위한 RMI(Remote Method Invocation)가 존재하며, 다른 JVM 객체의메소드를 호출할 수 있다

요청을 위한    stub, 요청 처리에 skeleton 이라는 객체를 이용하여 통신을 수행함



**"무기력한 도메인  모델(anemic domain model**)**"이란**

먼저 도메인 모델이란 말 그대로 도메일에 대한 모델, 여기서 도메인(domain)은 sw 프로그램 개발에 필요한 요구사항, 기능 같은 정의 / 해결해야 할 문제들에 대한 영역이다

도메인 모델은 이런 도메인을 다이어그램 같은 형태로 표현한 것으로, 필요한 객체들 자체와 이들의 역할 및 그 안의 속성들, 객체들 간 관계 등의 표현되어야 한다

무기력한 도메인 모델이란 도메인 모델이 DTO 마냥 get\~, set\~으로만 이루어져 단순 데이터 짬통으로 이용되고, 해당 도메인 모델을 이용하는 서비츠 층쪽에 비즈니스 로직이 편중되어 있는 경우를 말한다



**이것이 안티패턴인 이유? -> 안티패턴 : 비효율적이거나 생산성 떨어지는 권장되지 않는 설계 패턴**

이러한 무기력한도메인 모델은 "객체는 상태와 행동을 모두 가진다" 는 객체지향의 원리에 위배되며, 도메인 로직은 도메인 영역에 표현되야 한다는 도메인 주도 설계(DDD)에도 위반한다

이렇게 무기력하게 개발할 경우코드의 길이가 기하급수적으로 길어지고 여러 사람을 거치게 되는 현장에서 각 담당자들이 코드의 의미를 제대로 이해하지 못하고 나중에 다시 봤을 때 잊어버리게 될 것이다



**자바빈즈(javajeans)**

자바빈즈는 자바로 작성된 sw 컴포넌트로 실행중인 JVM 프로세스 내에서 인스턴스가 동작한다

로직 부분을 분리하여 재사용함으로서 효율을 높이기 위한 목적으로 쓰이며, 지켜야 할 몇가지 관례가 존재함

* 클래스는 직렬화되어야 함
* 클래스는 기본 생성자는 가져야 함
* 클래스 속성들은 get, set 등의 메서드를 가지고 접근 가능하여야 함
* 클래스는 필요한 이벤트 처리용 메서드를 포함하고 있어야 함



**EJB(Enterprize Javabeans)**

서버 측 컴포넌트 모델로 일반적으로 비즈니스 로직을 가지는 서버 어플리케이션을 뜻한다

IT 기술의 발달로 서비스 측은 트랜잭션, 멀티스레드 등 여러 기술들이 요구될 뿐만 아니라 비즈니스 로직까지 고려하게 되었는데, 복잡한 구조의 대규모 시스템의 분산 객체 환경을 쉽게 구현하기 위해 등장했다

EJB는 컴포넌트 기반 개발 모델을 제시하여 개발자가 모데인과 비즈니스 로직에만 집중할 수 있게 한다

EJB의 대표적인 특징으론,

* 객체를 미리 생성하고 메모리에 저장하여 사용준비 상태에 들어감(인스턴스 풀링)
* container가 자동으로 모든 메소드에 대한 트랜잭션 처리를 해줌
* 분산기능 지원

등이 있다

다만 EJB로 개발 시 객체지향의 특징과 장점을 포기해야 하고 프로그래밍이 복잡하며 객체구조가 컨테이너 내에서만 작동 가능하다는 단점들도 존재했다

\-> 이러한 문제들을 개선하기 위해 등장한 것이 Spring : 장점은 유지하면서 복잡성, 단점들은 제거



**Java의 record**

불변 데이터 객체를 쉽게 생성할 수 있는 새로운 유형의 class로 JDK16에서 정식으로 등장함

public record 객체명(매개변수) { } 형태로 선언하며 생성자 작성 없어도 자동으로 get, set, toString, equals 등의 메소드 구현 제공한다

암묵적으로 final 클래스라 상속 불가 및 abstract 선언도 불가능하며, 다른 클래스를 상속(extends)받을 수도 없음



**DAO**

DAO는 data access object의 약자로 말 그대로 데이터 접근에 관한 객체로 접근 로직과 비즈니스 로직을 분리하기 위해 사용된다

데이터베이스에 직접 접근하여 CRUD 작업을 수행한다



**ORM**

ORM은 Object relational mapping의 약자로 프로그래밍 상 객체와 DB 데이터간에 매핑을 수행한다

객체 개념을 구현한 클래스와 DB 상의 테이블을 매핑 시 맞지 않는 부분이 나오는데 ORM을 통해 객체 간 관계를 가지고 SQL 쿼리를 자동으로 생성하여 이러한 문제를 해결할 수 있다













****



&#x20;