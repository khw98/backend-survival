# HTTP server

**Java ServerSocket**

앞장에서 "소켓을 통한 서버 - 클라이언트 간 통신 순서"의 서버측이listen 단계 역할을 수행하기 위한클   래스



**Blocking vs Non-Blocking**

blocking은 함수 A가 함수 B를 호출했을 때, B가 자기 작업이 끝날 때까지 A에게 제어권을 주지 않는다

non blocking은 반대로 제어권을 바로 A에게 넘겨줘서 A가 다른 일도 할 수 있게 한다

자바에서 blocking에 대한 대표적인 예시로는 IO 작업이 있는데, 예를 들어 InputStream에서 read나 OutputStream에서 write 메소드 같은 읽고 쓰는 작업이 있을 경우 데이터가 입/출력 되기 전까지 blocking 상태가 되어 다른 일을 하지 못한다

이러한 문제를 해결하기 위해 따로 non blocking 방식으로 IO작업을 수행하는 NIO 가 등장하기도 했다







