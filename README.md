# SpringBoot Docker 실행

## 1. Docker 샘플 프로젝트 만들기
    
- gradle `spring-boot-starter-web` 의존성 추가

   ```groovy
   dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-web'
    testImplementation 'org.springframework.boot:spring-boot-starter-test'
   }
   ```
## 2. Dockerfile 생성 및 작성 

- ### Dockerfile 생성

  - #### Dockerfile
  - 
     ```dockerfile
    
        FROM openjdk:17
        ARG JAR_FILE_PATH=build/libs/docker-0.0.1-SNAPSHOT.jar
        COPY ${JAR_FILE_PATH} app.jar
        ENTRYPOINT ["java","-jar","app.jar"]
    
     ```

  - #### docker-compose

     ```yaml
      # sample
     ```

## 3. Gradle build 및 Docker image 
- [Gradle Project 생성 및 빌드](#gradle-project-생성-및-빌드)
- [Docker Build 및 image 생성](#docker-build-및-image-생성)
- [Docker Image run](#docker-Image-run)
- [Docker container 종료](#docker-container-종료)
- [Docker container 강제 종료](#docker-container-강제-종료)
- [Docker container 삭제](#docker-container-삭제)
- [Docker image 삭제](#docker-image-삭제)

- ### Gradle Project 생성 및 빌드 
  
  ```
    ./gradlew clean build
  ```

- ### Docker Build 및 image 생성

  ```
  docker create [image]
  docker build -t [image]
  ```

- ### Docker Image run

   ```
   docker run [image]
   docker run -d [image]
   docker run -d -p 8080:8080 [image]
   ```
  
- ### Docker container 종료
  
  ```
  docker stop [container]
  ```

- ### Docker container 강제 종료
  ```
  docker kill [container]
  ```

- ### Docker container 삭제
  ```
  docker rm [container]
  ```


- ### Docker image 삭제

  ```
  docker rmi [image id]
  docker rmi [image name]
  ```


### 참고자료
- [Docker 공식문서](https://docs.docker.com/engine/reference/)
- [Spring Docker 가이드](https://spring.io/guides/topicals/spring-boot-docker)

