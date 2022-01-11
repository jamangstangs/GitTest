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
- @@@@@현재 시점을 기준으로 Commit을 새로 만들어보겠다. 
  - 이 시점은 GitTest2에서 진행한 파일이다.
  - 잠깐, remote 업데이트 해보자. 

## Soruce Tree 사용하기

1. GitCommnad 파일 수정하기
2. 새로운 파일 하나 더 만들어주기. (GitList.md)

- origin : 우리가 연결한 GitHub의 원격 저장소의 닉네임이다. git remote add (myorigin) https://github.com/jamangstangs/somthing으로 원격 저장소를 애드하면 된다. 
- master : 커밋을 오릴는 줄기의 이름이다. 
  - master : 로컬 저장소의 줄기 이름이다. 
  - origin/master : 원격 저장소의 줄기 이름이다. 
- push를 하면, 
  - master origin/master 이렇게 동기화 된다. 

## Git 정리하기

- add : 변경사항을 선택한다. 
- commit : 변경사항을 하나로 묶어서 
  - **바뀐 부분만 저장 x -> 전체를 저장한다.** 
    - **차이점만 저장 : 거슬러 올라갈 때 바뀐점을 모두 반영하는 계산을 한다. 백번 바뀌면, 100번을 연산해야한다.** 
    - **모두 저장 : 현재랑 그때 당시의 커밋만 비교하는 연산만 하면 된다.** 

## 파일의 4가지 상태

1. 추적 안된 파일 : git add 안함
2. 스테이지 됨 : git add 함, 아직 commit은 안해서 스냅샷을 못찍은, 버전으로 만들어야함.
3. commit됨 : 하나의 버전을 만들었다. 하지만, 로컬에서 버전 관리만 가능해서 push 명령어를 써서 원격 저장소에 올려야 한다. 
4. push됨 : 원격 저장소에 올렸다는 뜻이다. 

즉, 파일의 상태는 총 4가지이다. 

1. 추적 안됨 : 아직 init안함
2. add 이후, 상태는 3가지로 나뉜다. 
   - 수정없음 : 수정 사항이 없어서 그대로이다. 
   - 수정함 : add 이전에, 수정을 했다. 
   - 스테이지 됨 : 수정사항을 add했다. 

# 협업

## 원격 저장소에서 협업하기 : Branch

- 두명이 최신 버전을 각각 따로 작업한다고 하면

- 버전1

  - 오징어의 버전2
  - 고양이의 버전2

- 각각의 버전2는 버전 1을 가리키고 있다. 

- 버전 1을 기준으로 나누어서 작업할 수 있는 기능을 **Branch라고 한다. **

- master : 줄기

- master줄기가 

  - 오징어 branch
  - 고양이 branch

  두 갈래 길로 나뉘었다. 

- 이를 어떻게 넘나들까 ? -> HEAD라는 특수한 포인터. 

- **HEAD : 이를 통해서 커밋을 넘나는다. **

  
