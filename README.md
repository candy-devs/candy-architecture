# candy-architecture

캔디 개발 노트

 - Fronet-end: Next.js
 - Back-end: Spring Boot, Node.js, Python3, Go

## Backend

### Java

 - [ ] Module을 통한 도메인 분리
 - [ ] Spring Cloud 적용
 - [ ] Serverless를 위한 GraalVM AOT native-image 빌드로 가벼운 이미지 배포

### Micro Service

 - [ ] DevOps 구축
   - [x] CI/CD Script 작성
   - [ ] Ansible Script 작성
   
 - [ ] Kubernates 공부
   - [ ] Service Mesh: Istio
   
 - [ ] Apps
   - [ ] Spring Backend Deployment
   - [ ] Image Resize Server
   
 - [ ] Spring Cloud 적용
   - [ ] Service Divide
     - [ ] 유저, 커뮤니티 Read, Write 서버 분리 (예정)
     - [ ] 로드 테스트로 분리 근거 남기기
   - [x] Spring Boot Actuator
   - [ ] Spring Cloud Config
   - [ ] Spring Cloud Netflix Eureka
     - [ ] Spring Cloud Load Balancer Client
   - [ ] Spring Cloud Resilience4j
   - [ ] Spring Cloud Gateway
   - [ ] Spring Cloud Stream (Kafka)
   
 - [ ] ELK Logging 스택 구축
   - [ ] Micro Service App 프로젝트 Id 규칙 및 로깅 전략 설계

### Database

 - [ ] PostgreSQL, LLVM Jit을 통한 쿼리 튜닝
 - [ ] Redis, MongoDB를 통한 정적 자료 캐시 및 조회 제공
 
### Ingress

 - [ ] API
   - [ ] API Server: http://server/api/v1/
 - [ ] Static
   - [ ] Image Serving: http://cdn/img/url.ext
   - [ ] Raw Image Serving: http://server/static/raw/from/s3.ext
 
### Micro Apps

#### Backend

##### Auth

- OAuth2.0
  
  ![OAuth](https://user-images.githubusercontent.com/9719650/177562962-981d31e6-545c-4e57-9847-b1fed46bcd7e.jpg)
  
  1. [Backend] Redirect to `/oauth2/authorization/[naver|kakao|facebook|google]`
  2. [Client] Login and Authorization on OAuth2.0 Provider
  3. [Backend] Redirect to `/login/oauth2/code/[naver|kakao|facebook|google]?state,code,scope`
  4. [Front] Redirect to `/` 

- Session

  ![Session](https://user-images.githubusercontent.com/9719650/177559067-63c704a6-502b-4047-a32d-db8f56b50a0b.jpg)
  
- JWT (external API)

  ![JWT external API](https://user-images.githubusercontent.com/9719650/177564783-10bcaf31-cb92-4ffc-9d82-f9ebbd00bc6e.jpg)

#### Image Resize App

![Resize](https://user-images.githubusercontent.com/9719650/177554309-a15826a2-cfe1-40f8-bf1c-97ed5605c1d4.jpg)

트래픽을 줄이기 위한 이미지 리사이징

 - [x] S3 Presigned Image URL
 - [ ] S3 Raw Image Upload (front)
 - [ ] SQS 연동
 - [ ] Node.js 기반 Sharp App
 - [ ] Node.js 기반 Image Proxy App (Sharp App이랑 통합가능한가?)
   - [ ] CDN Fail시 CDN 적재 (LRU)

#### Article Search App

![Article Search](https://user-images.githubusercontent.com/9719650/178878037-7cbd0337-ddab-4537-950c-17bb6e12f909.png)

 - [ ] Elastic Search에 넣는다.
 - [ ] 수정 요청이 들어오면 수정 사항을 반영한다.
 - [ ] 삭제 요청이 들어오면 해당 Article를 ES에서 삭제한다.
 - [ ] 검색 요청이 들어오면 검색한다.

#### Hot Article Picker App

 - [ ] 구현 

#### Hot Tag Picker App

 - [ ] 구현 
