# 젠킨스 튜토리얼

- 도커를 사용해 젠킨스 이미지를 불러오고 컨테이너 실행시켜 기본 설정을 진행하고 젠킨스를 통해 파이프라인을 구축하는 방법을 알아봅니다.

## 젠킨스 이미지 불러오기

- `docker pull jenkins/jenkins:lts-jdk11`로 LTS버전의 젠킨스 이미지를 불러옵니다.

## 젠킨스 실행하기

- `docker run --name jenkins -p 8080:8080 -v jenkins:/var/jenkins_home jenkins/jenkins:lts-jdk11`로 컨테이너를 실행시키고 8080번 포트로 접속합니다.

## 젠킨스 어드민 password 입력하기

- `docker exec`을 사용해 실행중인 젠킨스 컨테이너에 명령어를 전달하거나 `docker exec it [컨테이너 ID] bash`로 컨테이너 내부에 셸을 실행시켜 직접 `/var/jenkins_home/secrets/initialAdminPassword`의 파일의 내부를 확인해서 password를 가져와 젠킨스를 Unlock 시킵니다.

## 어드민 계정 생성

- 계정명, 암호, 이름, 이메일 주소를 입력해서 어드민 계정을 생성합니다.

# 파이프라인 구축해보기

- Create job을 눌러 새로운 item의 이름을 정해주고 pipeline을 선택해서 생성합니다.

- Pipeline 항목의 definition에서 Pipeline script from SCM을 선택합니다.

- 배포 자동화 파이프라인을 구축할 깃 레포지토리의 URL을 입력하고 스크립트가 실행될 젠킨스 파일의 경로를 지정해주고 적용시킵니다.

- 젠킨스 파일에 단계 별로 수행될 스크립트 내용을 명시하고 깃 레포지토리에 push 합니다.

- 젠킨스 대시보드에서 빌드를 눌러 성공한 빌드의 콘솔 출력 내용을 확인하면 단계 별로 명시한 명령어가 실행된 것을 볼 수 있습니다.

- ![image](/jenkins-tutorial/jenkins-first-pipeline-as-code.PNG)
