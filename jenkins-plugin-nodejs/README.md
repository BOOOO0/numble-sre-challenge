# 젠킨스 플러그인 설치

- Jenkins 관리 -> Plugin Manager에서 Available plugins 중 NodeJS 플러그인을 설치합니다.

- 플러그인을 사용하기 위해서는 Global Tool Configuration에서 NodeJS에 대한 플러그인을 등록해야 합니다. 이 과정은 젠킨스에 환경변수를 등록하는 것과 같습니다.

- nodejs 환경변수를 등록하고 이전의 파이프라인 구축 튜토리얼과 마찬가지로 젠킨스 파일을 작성하고 NodeJS 플러그인에서 제공하는 스크립트를 사용해서 `npm install`과 `npm run start`를 빌드 단계에 실행되도록 합니다.
