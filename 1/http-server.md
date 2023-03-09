# HTTP server

**Java ServerSocket**

앞장에서 "소켓을 통한 서버 - 클라이언트 간 통신 순서"의 서버측이listen 단계 역할을 수행하기 위한클   래스



**Blocking vs Non-Blocking**

http-server 에서 구현한 server 측 코드는 전형적인 blocking 방식이라고 볼 수 있다

while문 내에서 listen에 대한 accept를 하고 이에 대한 응답을 보내게 되는데, 요청한 클라이언트 별로 스레드를 만들고, 클라이언트 대한 IO작업을 진행하는 동안 그에 대응하는 스레드는 blocking 된다

클라이언트 수가 많아질 수록 스레드의 수도 늘어나 cpu 관점에서 비효율적인 작업을 하게 되는데,&#x20;

이러한 blocking 방식의 단점을 해결하기 위해 나온 것이 non blocking(NIO) 방식이다



Non blocking은 말 그대로 IO 작업 진행 중에 스레드를 block시키지 않는다 ->&#x20;





