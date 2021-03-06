### Git : (분산) 버전 관리 프로그램. 로컬저장소 ###

- 버전 : 컴퓨터 소프트웨어의 특정 상태
- 관리 : 어떤 일의 사무, 시설이나 물건의 유지. 개량
- 프로그램 : 컴퓨터에서 실행될 때 특정 작업을 수행하는 일련의 명령어들의 모임

**그렇다면 버전 관리란?**  쉽게 말해서 최종, 최최종 ..... 

**용량이 너무 크면 ? ** 수정부분을 기록한 파일 + 최종 파일 저장

**수정부분 기준의 파일이 궁금하면?** 최종 파일로부터 되돌아가기



**중앙 집중식 버전 관리** : 중앙 서버에서 모든 버전을 관리

-> 서버 파일이 날라가면 모두 초기화됨..

**분산 버전 관리 ** : 사용자에게 분산하여 버전 관리

```markdown
git 의 상태

1. untracked : 처음으로 관리되는 대상. 빨간색으로 표시 됨
- working derectory에 있고, staging area에 올라가기 전
2. tracked : 관리중인 대상
- git add 시 new file (초록색) 으로 표시됨. staging area에 올라감
```



```markdown
파일을 깃허브에 올리는 과정

실제폴더 -> 로컬저장소 (git) -> 원격저장소 (github)
1. git init : 실제폴더에서 깃으로 이동. 깃으로 관리하겠다. 뒤에 master 붙음
  - 이 단계에서 반드시 git status로 확인하기. add 하면 안되는 파일 반드시 걸러내기.
2. git add : 깃 working directory -> staging area 
  - 이 단계에서 반드시 git status로 확인하기. commit 하면 안되는 파일 반드시 걸러내기.
3. git commit : 버전 관리.
4. git log : 커밋 사항 확인하기.

원격저장소(github - remote repository)에 올리기
1. 원격저장소 정보(url) 등록
 : git remote add origin url
2. 로컬 내용을 push 한다.
 : git push -u origin master
3. 권한 실행 하고 깃허브에서 확인하기.
```



### Github  : 서비스. 깃을 업로드하여 관리하는 네트워크서비스, 포트폴리오로 사용됨. 원격저장소

