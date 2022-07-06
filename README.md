# candy-micro-services-plan

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

  
- Session

  ![Session](https://user-images.githubusercontent.com/9719650/177559067-63c704a6-502b-4047-a32d-db8f56b50a0b.jpg)
  
- JWT (external API)

  ![JWT external API](https://user-images.githubusercontent.com/9719650/177562065-a4493608-6bbf-4e7b-b2f6-e28cfc39f9ef.jpg)


#### Image Resize App

![Resize](https://user-images.githubusercontent.com/9719650/177554309-a15826a2-cfe1-40f8-bf1c-97ed5605c1d4.jpg)

트래픽을 줄이기 위한 이미지 리사이징

 - [x] S3 Presigned Image URL
 - [ ] S3 Raw Image Upload (front)
 - [ ] SQS 연동
 - [ ] Node.js 기반 Sharp App
 - [ ] Node.js 기반 Image Proxy App (Sharp App이랑 통합가능한가?)
   - [ ] CDN Fail시 CDN 적재 (LRU)
