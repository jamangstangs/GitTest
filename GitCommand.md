## Start

- git init
- git add ()
- git commit -m "   "
이렇게 하면 local에 버전관리를 시작한다. 
## Version Control
- git log : 커밋 로그를 확인한다. 
    - 원하는 커밋 주소를 복사하고 
- git checkout 109unfafnjsfas
    - 원하는 커밋으로 돌아간다. 
- git checkout - 
    - 최신 커밋으로 다시 돌아간다. 
## 원격 저장소 추가하기

- 플러스 눌러서 내 깃허브 원격 저장소에 새로운 Repository를 추가하자. 
  - 해당 Repository의 주소를 받아서 내 로컬 저장소에서 만든 커밋들을 remote Repo에 넣어보자. 
- git remote add origin https://github.com/jamangstangs/GitTest.git
  1. Origin : remote 계정을 의미한다. 
- git push origin master
  - 안됨. 개인 토큰 생성 방식으로 다시 설정하자.
  - 계정 : 그대로 입력
  - 비밀번호 : 토큰 값을 입력하자. 

## 원격 저장소의 커밋을 로컬 저장소에 내려받기

- Clone : 원격 저장소의 버전 전체를 내 로컬로 받는 것을 의미한다. 
- git clone https://jamangstangs/GitTest.git .
  - 마지막에 점 찍어줘야 폴더를 안에 생성 안한다. 
