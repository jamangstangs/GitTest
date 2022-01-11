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

- @@@@@ 이 시점을 기준으로 feature/branch라는 브랜치에서 수정을 할 것이다. 여기서 수정한 사항은 feature branch라는 브랜치에서 수정한 것이다. 

- new.md라는 파일을 만들어보자. 

- gitList.md를 수정해보자. 




## 브랜치와 브랜치를 합치기 : Merge

- feature/branch
  - GitCommand 작성
  - GitList : 여기서 3번 항목 충돌 예정
  - new.md 생성
- feature/otherBranch
  - Gitcommnad 유지
  - GitList : 여기서 3번 항목 충돌 예정
  - otherNew.md 생성
- 이제 GitList에서 충돌이 일어날 예정이다. 
  - feature/branch
  - feature/otherBranch
- 우선, master branch를 feature/branch로 빨리감기 할 것이다. 
- 이제, master branch에 feature/branch의 내용이 반영되었으니, feature/branch는 지워도 된다. 
- 이제, feature/otherBranch에서 수정 사항을 지금의 master branch에 합치고자 한다. 
  - 문제점
    - master가 featrure/branch를 기준으로 변화됨. 하지만 분기점으로부터 생성된 변화들이 다르다. (위에 참고하기.)
    - 이렇게 되면, GitList에서 충돌이 일어날 예정이다. 어떻게 처리할지 알아보자. 
- master branch를 기준으로 merge해보자. 
  - ??? branch 기준으로 merge : master branch에 변경사항을 반영한다는 뜻이다. 

## Merge 실습하기.

- 실제로 Merge를 하고 다시 작성하러 오겠다. 
- feature/branch를 병합을 마치고 온 상태이다. (빨리감기 병합)
- 이제, feature/otherBranch를 병합해야하는데, 충돌이 에정되어있다. 
- 합치는 방법
  1. master branch를 내가 작업중인 branch에 땡겨와서 병합해보고, 문제가 없는지 확인한다. 
  2. 병합에 문제가 없으면, master branch에 반영한다. 
- 자. 이제 , feature/otherBranch 커밋하고 체크아웃해서 master를 feature/otherBranch를 기준으로 병합을 하러 가보자. 

## Merge 실습 정리

1. feature/branch를 master에 병합 -> 문제가 없다. 
2. feature/otherBranch에서 master를 땡겨와서 병합 -> 이전에 feature/branch에서 master로 병합했을때 충돌이 일어나는 부분이 발생했다. 
3. 직접 코드를 수정해서, 다시 commit을 올린다. 
4. 로컬에서 병합 과정 중 일어난 충돌을 해결함.
5. origin master에 푸쉬 하면서 원격 저장소를 최신버전으로 유지한다. 

## Pull Request

- 충돌 해결했다고 무작정 내 브랜치를 master branch에 병합하는게 말이 되는건가?

  1. 내가 master branch에 병합하고자 한다. 
  2. 사수의 허락을 거쳐야 한다. 

  이때, 예의 바르게 허락을 받는 것이 풀 리퀘스트이다. 

- Pull Request 과정 정리

  1. feature/login branch 생성하고, 해당 branch에서 작업을 한다. 
  2. commit하고 origin/feature/login으로 푸시한다. 
  3. github에 들어가서 compare & pull request 버튼을 선택한다. 
  4. 여기서, origin/master에게 권한이 있는 사람에게 pull request를 진행한다. 
  5. 이것을 진행하면, pull request를 허락한다. 
  6. 이후, local의 master에서 fetch해줘서 그래프를 업데이트 해준다. -> origin/master에 feature/login이 들어간 것을 볼 수 있다. 
  7. 이제, local의 master를 pull해줘서 origin/maseter 에서 끌어온다. 

- **pull : 원격 저장소에서 코드를 끌어온다.** 

- **fetch : 원격 저장소의 변화를 그래프로만 그려준다.** 

## Release : 개발이 완료되어서 출시한다. 

- Version : 프로그램을 출시할 때 업그레이드 할 때 버전을 명시한다. 
- 이를 **깃에서는 tag로 표현한다. **
- 간단하게, master branch에 v1.0.0이라는 태그를 달아보자. 
- 















