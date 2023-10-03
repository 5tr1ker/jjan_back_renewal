# JJan ( 2023 - 6 ~ 2023 - 8 )

> 친목을 위해 모임을 개설하고 만남을 갖는 웹 서비스

![image](https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/d8d3e223-ff8d-4490-a872-f407b1ba8296)

<h2>Project Introduce</h2>
휴일에 같이 술 마실 친구가 없어 한가한 일상을 보내는 사람들을 위해 술자리 모임을 만들거나, 모임에 쉽게 참여할 수 있게 도와주는 웹 서비스입니다.<br/>

<h3>주요 기능</h3>
프로젝트 주요 기능은 다음과 같습니다.<br/><br/>

- 사용자 : 회원 가입 , 로그인
- 모임 : 모임 개설 , 모임 참여

<h2>Project Structure</h2>

- Front-End
    - TypeScript
    - React
    - Styled-components
    - Axios
- Back-End
    - Spring Boot
    - Spring Security
    - Spring Data Jpa
    - HTTP API ( Rest API )
    - MySQL ( RDBMS )
    - Jenkins
    - Swagger
    - AWS S3 & EC2

<h2>ERD</h2>

![image](https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/103cd299-eade-4fdc-b34e-172de446325d)

<h2>Spring Security</h2>

> 권한에 따라 접근할 수 있는 API 를 분리했습니다.

- CSRF : disable
- password encryption : BCryptPasswordEncoder
- Session Creation Policy : STATELESS
- JwtAuthenticationFilter : before UsernamePasswordAuthenticationFilter.class

<h2>CI / CD</h2>

> Jenkins 를 이용하여 지속적인 배포를 구성

- 병합된 코드는 Jenkins WebHook 을 통해 AWS 에 호스팅됩니다.

<h2>1. 로그인 & 회원가입 화면</h2>

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/cb6e6068-87d4-4844-9f6d-497ceb76c066" width="25%">

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/67ec498b-f048-4bef-9720-4e59336097e6" width="25%">

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/27de3f8b-d33b-4bd0-a98e-af6dea99a762" width="25%">

- 로그인 시 발급되는 AccessToken 과 RefreshToken 은 쿠키에 보관됩니다.
- 쿠키는 XSS 공격을 막기 위해 HTTPOnly 옵션을 설정했습니다.

<h2>2. 모임 목록</h2>

> 현재 참여하고 있는 사용자와 마감 날짜가 노출이 됩니다.

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/bc623c0d-2daa-451d-a9d5-7495671bad92" width="25%">

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/3029f246-78ee-4956-a19a-be059d064ce0" width="25%">

- 마감이 가까운 모임이 먼저 사용자에게 노출됩니다.
- 필터를 통해서 내가 원하는 모임을 빠르게 찾을 수 있습니다.

<h2>3. 모임 상세 정보</h2>

> 모임에 대한 상세 정보를 노출합니다.

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/9b6bd47d-1571-4867-96b7-cd0205376bf2" width="25%">

<h2>4. 모임 개설</h2>

> 모임을 직접 개설할 수 있습니다.

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/083803c6-a6a8-4438-ab7b-ec530ea98920" width="25%">

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/8eee1308-24e3-4e97-9e49-3accd2f3f252" width="25%">

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/5a0b2f33-1536-43bf-a72c-8ab0303dd025" width="25%">

<h2>5. 프로필 정보 수정</h2>

> 사용자에 대한 정보를 수정할 수 있습니다.

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/647c67a3-450e-407d-9482-2c0783ef7a1d" width="25%">

