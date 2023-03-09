# Java HTTP server

**Java HTTP Server**

내부적으로 non blocking 방식으로 IO를 처리하는 고수준 HTTP 서버 API로 com.sun.net.httpserver 통해 이용할 수 있다

HttpServer 대한 객체를 생성 -> 해당 객체.createContext 진행 -> 객체.start() 로 서버를 실행할 수 있음



**Java NIO**

자바는 C++ 과 달리 IO 작업 시 커널 영역의버퍼에서 JVM 버퍼로 데이터를 옮겨주는 추가적인 과정이 필요하여 IO 효율이 떨어진다

이러한 IO 성능 문제 해결을 위해 나온 패키지가 java.nio로, nio는 양방향 입출력이 가능한 채널을 통해 버퍼에서 직접 데이터를 읽어와 IO 작업의 효율성을 올릴 수 있다

또한 기존 자바 IO작업이 blocking 형태로 진행되어 데이터 read(), write() 호출 시 IO 작업 완료 시까지 스레드가 block 되고 인터럽트로 빠져나갈 수도 없었는데, java nio는 스레드가 block 되지 않고 현재 상태에서 즉시 반환을 수행한다

IO와 NIO 각각의 특징을 정리하자면 기존 IO방식은 클라이언트 수가 적고 대량의 입출력이 필요할 때에,

NIO 방식은 클라이언트 수가 많고 IO 하나하나의 처리가 빨리 끝날 수 있을 때에 더 적합할 것이다





**Java Lambda expression**

람다식이란 익명 함수의 일종으로 객체 생성같은 과정 없이   (매개변수) -> {실행코드} 형태로 코드를 더 간결하게 나타낼 수 있다

\-Java Functional interface : functional interface는 1개의 추상 메소드를 가지는 인터페이스를 말하며&#x20;

그 외의 메소드 개수는 상관없음, 여기서 추상 메소드는 구현부가 없는 메소드를 말한다

람다식에 functional interface의 매개변수, 리턴 타입만 맞추면 쉽게 호출할 수 있다







