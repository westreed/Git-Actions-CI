# 사용할 기본 이미지 지정
FROM openjdk:17-jdk

# 작업 디렉토리 설정
WORKDIR /app

# xargs 설치 -> gradlew 빌드시 xargs가 요구됨
RUN apt-get update && apt-get install -y xargs

# 프로젝트 파일 복사
COPY . .

# Gradle 실행권한 부여
RUN chmod +x ./gradlew

# Gradle 빌드
RUN ./gradlew build

# JAR 파일 실행
CMD ["java", "-jar", "./build/libs/test-app.jar"]