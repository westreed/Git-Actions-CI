# Git-Actions-CICD

Git Actions을 활용한 CICD 공부

## Step

1. GitActions에서 Dockerfile을 통해 이미지를 빌드함.
2. 빌드된 이미지를 DockerHub에 업로드.
3. AWS EC2 SSH 연결로 접속.
4. docker-compose.yml 파일을 EC2로 옮기고 실행하여 업로드된 이미지를 다운받고 실행.

## AWS CodeDeploy를 사용하는 방향으로 전략을 재수립해보기

1. GitActions에서 스프링 프로젝트를 빌드.
2. 빌드된 파일을 기반으로 Dockerfile을 통해 이미지를 빌드함.<br>
// 위에서는 Docker에서 빌드를 처리했지만, GitActions에서 빌드하는게 시간절약이 되는 것 같음.
3. AWS ECR에 로그인함. 이로써 도커이미지를 푸시할 수 있음.
4. 생성된 도커 이미지를 ECR에 푸시함.
5. AWS ECR과 S3를 기반으로 AWS CodeDeploy를 통해 EC2에 배포.
