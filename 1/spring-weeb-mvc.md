# Spring web MVC



**Spring Boot**

스프링부트는 사용자가 스프링으로 프로젝트를 만들고시작(boot)할 때 필요한 사전 설정 등을 자동으로 처리 혹은 단순화 시켜주는 프레임워크이다



Spring initializer

스프링 프레임워크에서 빌드, 언어, 버젼 등을 선택하고사용할 라이브러리를 검색을 통해 쉽게 찾고 추가할 수 있게 해주어 프로젝트 생성을 도와주는 웹 도구이다



Web Server와 Web Application Server(WAS)

웹 서버는 클라이언트로부터 http 요청을 받으면 그에 대한 이미지 파일이나 html 문서 같은 단순하고 "정적인" 컨텐츠를 제공한다

WAS는 DB 조회 등을 요구하는 더욱 복잡하고 동적인 컨텐츠를 클라이언트에게 제공하기 위한 Application server이다

<figure><img src="../.gitbook/assets/톰캣.PNG" alt=""><figcaption></figcaption></figure>

Tomcat이 WAS의 대표적인 예이며 java 기반이다



Model-View-Controller(MVC) 아키텍처 패턴

application을 3가지 컴포넌트로 나누어 각자가 고유의 역할을 수행하도록 하고 결과물을 다른 컴포넌트 혹은 유저에게 넘긴다

1. View : 사용자에게 보여지는 부분(GUI)
2. Controller : 사용자의 입력에 대한 처리, 요청에 대해 view와 model에게 필요한 내용 전달
3. Model : 앞의 둘을 제외한 나머지 부분, 변수나 상수 데이터 등



\-관심사의 분리(Seperation of Concern) : SW 개발 원칙 중 하나로, 소프트웨어를하나의 커다락 block으로 만들지 말고 관심사 별로 블록을 나누는 것이다

이렇게 함으로써 특정 관심사에 대한 이슈가 생겨고 그에 맞는 block 위주로 확인하면 되니 유지보수가 편해지고, 각 관심사에 따라 개발 인력을 배치하기도 좋다



Spring MVC







