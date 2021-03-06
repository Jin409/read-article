## HTTP와 HTTPS의 개념 및 차이점
https://mangkyu.tistory.com/98<br>
++ https://blueyikim.tistory.com/1999 HTTP의 구조 - 헤더와 본문<br>
++ https://www.uname.in/129 - 대칭키 vs 공개키(비대칭키) 암호화 차이<br>

### 1. HTTP란
- 서버/클라이언트 모델을 따라 데이터를 주고받기 위한 프로토콜
- 80번 포트를 사용
- 하이퍼텍스트를 교환하기 위한 통신 규약
- 서버는 80번 포트에서 요청을 기다림 <-> 클라이언트는 80번 포트로 요청을 보냄

  #### HTTP의 구조
  - TCP/IP 위에서 작동
  - 상태가 없는 프로토콜
  - Method / Path / Version / Headers / Body 로 구성됨
    - Method ex) GET
    - Path ex) Get/HTTP/1.1
    - Version ex) 위에서의 1.1
    - Headers 본문 및 요청/응답에 대한 정보 / 이름-값 쌍으로 설정됨 
  - 암호화되지 않은 데이터 전송에 쓰임 => 보완하기 위해 https가 등장

  #### + HTTP헤더의 유형
  1. 일반 헤더 : 본문과 관련 없음. 요청, 응답이 생성된 날짜와 시간에 대한 정보
  2. 요청 / 응답 헤더 : 요청한 URL / 메소드 / 요청 생성에 사용된 브라우저에 대한 정보
  3. 엔터티 헤더 : 실제 전송중인 본문에 대한 정보 : 컨텐츠 길이 / 언어 / 인코딩 / 만료 날짜 등

### 2. HTTPS란
- 암호화가 추가된 프로토콜
- 443번 포트 사용

  #### 대칭키 암호화
  - 암복호화에 사용하는 키가 동일
  - 클라이언트, 서버가 동일한 키를 사용
  - 키가 노출되면 위험하지만 속도가 빠름

  #### 비대칭키 암호화
  - 암복호화에 사용하는 키가 다름 => 공개 / 개인
  - 1개의 쌍으로 구성된 공개키와 개인키를 암호화
  - 키가 노출되어도 안전 But 속도가 느림
  - 개인키를 암호화할 경우의 장점 : 내가 인증한 정보임을 알려 신뢰성을 보장
  - 공개키를 암호화할 경우의 장점 : 개인키는 나에게만 있어서 나만 볼 수 있음
 
  #### HTTPS의 동작 과정
  1. 클라이언트가 서버로 최초 연결 시도
  2. 서버는 공개키를 브라우저에 넘겨줌
  3. 브라우저는 인증서의 유효성 검사 => 세션키 발급
  4. 브라우저는 세션키 보관하며 추가로 서버의 공개키로 세션키를 암호화하여 서버로 전송
  5. 서버는 개인키로 암호화된 세션키를 복호화하여 세션키 얻음
  6. 클라이언트와 서버는 동일한 세션키 공유 => 데이터 전달시에 세션키로 암호화/복호화 
  


