# JJan ( 2023 - 7 ~ 2023 - 9 )

> 친목을 위해 모임을 개설하고 만남을 갖는 웹 서비스

<h2>Project Introduce</h2>

진행되고 있었던 프로젝트 중간에 참여하여 구현이 되어있는 로직에서 코드의 품질을 향상시키고 최적화하는 능력을 기를 수 있었던 프로젝트입니다. <br/>
또한 기능을 확장하고 기존 레거시 코드를 리팩토링할 수 있는 능력을 키울 수 있었습니다.

<h2>프로젝트 개요 & 주요 기능</h2>

휴일에 같이 술 마실 친구가 없어 무료한 일상을 보내는 사람들을 위해 술자리 모임을 만들거나,
찾고자하는 모임을 소개시켜주어 목적이 맞는 사람들과 함께 거부감 없이 빠르게 친해질 수 있게 도와주는 웹 서비스입니다.<br/>

- 사용자 : 회원 가입 , 로그인 , 프로필 수정 , 동네 인증
- 모임 : 모임 개설 , 모임 참여 및 탈퇴 , 모임 필터 탐색 , 상세 보기 , 관심있는 모임
- 채팅 : 모임 간 채팅

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

<h2>JPA & QueryDSL</h2>

> 객체 중심 설계와 반복적인 CRUD를 Spring Data JPA 로 최소화해 비즈니스 로직에 집중합니다.

- QueryDSL : 복잡한 JPQL 작성시 발생할 수 있는 문법오류를 컴파일 시점에 빠르게 찾아냅니다.
- Spring Data JPA 를 이용해 반복적인 CRUD를 최소화 하고 , 페이징을 이용해 성능을 높혔습니다.

<h2>Spring Security</h2>

> 권한에 따라 접근할 수 있는 API 를 분리했습니다.

- CSRF : disable
- password encryption : BCryptPasswordEncoder
- Session Creation Policy : STATELESS
- JwtAuthenticationFilter : before UsernamePasswordAuthenticationFilter.class

<h2>JWT</h2>

> JWT을 이용해 토큰 기반 인증 방식으로 사용자 인증 정보를 저장합니다.

- Access Token과 Refresh Token은 브라우저 쿠키에 저장되며 httpOnly 옵션으로 보안처리 했습니다

<h2>CI / CD</h2>

> Jenkins 를 이용하여 지속적인 배포를 구성

- 병합된 코드는 Jenkins WebHook 을 통해 AWS API 서버 에 호스팅됩니다.

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
  - 그 중 현재 내 위치랑 가까운 모임을 먼저 탐색할 수 있습니다.

<h2>3. 모임 상세 정보</h2>

> 모임에 대한 상세 정보를 노출합니다.

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/9b6bd47d-1571-4867-96b7-cd0205376bf2" width="25%">

<h2>4. 모임 개설</h2>

> 모임을 직접 개설할 수 있습니다.

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/083803c6-a6a8-4438-ab7b-ec530ea98920" width="20%">

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/8eee1308-24e3-4e97-9e49-3accd2f3f252" width="20%">

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/5a0b2f33-1536-43bf-a72c-8ab0303dd025" width="20%">

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/f4041ac5-a413-4892-b7b3-dfaa8e811f9f" width="20%">

- 카카오 API를 이용하여 모임에 대한 정확한 위치를 설정할 수 있습니다.

<h2>5. 프로필 정보 수정</h2>

> 사용자에 대한 정보를 수정할 수 있습니다.

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/647c67a3-450e-407d-9482-2c0783ef7a1d" width="25%">

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/48039bb5-58dd-40d6-8478-c63670924f65" width="25%">

<h2>6. 관심 목록 및 동네 인증</h2>

> 카카오맵 API를 이용하여 동네 인증을 구현했습니다.

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/ed560146-01e6-467c-b64a-c943c200a2bc" width="25%">
<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/68c0df08-820f-41db-afe8-85592624e9e1" width="25%">
<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/e884eb86-a225-4e63-9d60-a0fa2865a1d8" width="25%">

- 카카오맵 API를 이용하여 현재 사용자가 위치하고 있는 정보를 가져옵니다.

<h2>7. 채팅</h2>

> 현재 내가 속해있는 모임원들과 채팅을 할 수 있습니다.

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/496ddb19-7785-47b1-aa6e-fb9364e0336b" width="25%">

<img src="https://github.com/5tr1ker/jjan_back_renewal/assets/49367338/fe6bc3f5-242a-42d6-b3fc-c7bb63cc4345" width="25%">

- Socket 을 이용해서 각 채팅방마다 채팅을 할 수 있게 구현했습니다.
- 별도의 채팅방 가입을 할 필요없이 모임에 참여할 경우 자동으로 채팅방에 참여됩니다.
