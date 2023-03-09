# Java HTTP server

**Java HTTP Server**

내부적으로 non blocking 방식으로 IO를 처리하는 고수준 HTTP 서버 API로 com.sun.net.httpserver 통해 이용할 수 있다

HttpServer 대한 객체를 생성 -> 해당 객체.createContext 진행 -> 객체.start() 로 서버를 실행할 수 있음



**Java NIO**

자바는 C++ 과 달리 IO 작업 시 커널 영역의버퍼에서 JVM 버퍼로 데이터를 옮겨주는 추가적인 과정이 필요하여 IO 효율이 떨어진다

이러한 IO 성능 문제 해결을 위해 나온 패키지가 java.nio로, nio는 양방향 입출력이채가능한채널을 통해 버퍼에서 직접 데이터를 읽어&#x20;

