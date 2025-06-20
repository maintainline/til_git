# Git 관련 내용

- Git 은 파일의 버전을 관리하는 툴

## Git 설치

- https://git-scm.com/

![Image](https://github.com/user-attachments/assets/b696af00-17ca-454f-a091-935f4e912fd9)

![Image](https://github.com/user-attachments/assets/01d77df8-7fe0-4445-9c6f-fd89772725c8)

![Image](https://github.com/user-attachments/assets/572593d3-850b-4c0d-b603-c6a8836a6b8f)

- `아래는 반드시 VSCode 설치하고 나서 진행하여야 함. (목록 확인 필요)`
  ![Image](https://github.com/user-attachments/assets/8595c122-2615-47b9-bdf5-a8397923f525)
- 나머지는 기본 값으로 설치 완료함.

## Git 사용자 설정

- VSCode 에서 기본 터미널을 `Git Bash` 로 설정함.
- 터미널 실행 단축키 : `Ctrl + ~`
- 셋팅 아이콘 선택 > Setting 메뉴 선택
  ![Image](https://github.com/user-attachments/assets/db75dc81-2a39-471f-8d21-0737c7f7e9af)
- 검색에 `Terminal Default` 입력 > `Git Bash` 목록 선택
  ![Image](https://github.com/user-attachments/assets/fc81c5e2-8d81-4c8d-98f9-69138c1af66a)

## Git 정보 확인 및 셋팅 (터미널에서 진행)

- Git 버전 확인

```bash
git --version
```

- 기본 브랜치명을 `main` 으로 설정하기 (초기 설치시 master로 되어있음.)

```bash
git config --global init.defaultBranch main
```

- Enter 키를 통일시킴(맥, 윈도우, 리눅스가 Enter키, 줄 변경이 달리 처리됨)

```bash
git config --global core.autocrlf true
```

- git 수정 내역, 즉 commit 시 메세지 상세 남기기(VSCode로 작성 하도록 세팅)

```bash
git config --global core.editor "code --wait"
```

- 사용자 설정 (아이디, 이메일: google 계정과 github 아이디 추천)

```bash
git config --global user.name "wltjs6668"
git config --global user.email "wltjs6668@gmail.com"
```

# GitHub

- 회원가입(https://github.com) : 구글계정
- 예제) til_git 저장소 생성(생략)

## GitHub 사용자 계정 보안 설정

- 초기 설정시 다음 내용을 필수로 확인한다.

-`자격 증명 관리자` > Windows 자격증명 탭 > Git 관련 제거
![Image](https://github.com/user-attachments/assets/30fc1212-6d5c-44dd-aa3a-653855f9beae)

- Git 허브 자격증명 등록은 git push 진행되면 자동으로 로그인 팝업이 출력됨.

## Git 작업 및 GitHub 연결 작업 진행

### 1. 최초 프로젝트 관리를 Git 으로 설정

```bash
git init
```

### 2. 현재 프로젝트 상태보기

```bash
git status
```

### 3. git으로 파일 추적하기

```bash
git add README.md
```

### 4. Git 으로 모든 파일 추적하기

```bash
git add.
```

### 5. 작업히스토리 남기기

- 간단하게 메모 남기기

```bash
git commit -m "메세지"
git commit -m "깃허브 사용법 정리중"
```

- 여러줄 작업내역 작성하기

```bash
git commit
```

### 6. commit 내역 컨벤션 알아보기

```
[커밋타입] 커밋 메세지(옵션)

커밋 상세 내역

```

- 커밋 타입 : 업무의 분류

```
[feat] 새로운 기능 추가함
[fix] 버그 수정
[docs] 문서 수정(README.md 등)
[style] 코드의 스타일(띄워쓰기, 세미콜론 등)
[refector] 코드 리팩토링(기능변경, 코드 정리 등)
[test] 테스트 코드 추가한 경우
[core] 기타(빌드설정, 패키지 설정 등의 개발환경 변경 시)
```

- 옵션 : 23 번 이슈를 해결했고, 회원가입 로그인 기능을 추가했다.

```
[feat] 회원가입 로그인 기능 추가(#23)
```

### 7. commit 전체 내역 살펴보기

- 상세 보기

```bash
git log
```

-간략하게 보기

```bash
git log --oneline
```

- 하나의 commit 을 상세하게 보기(종료 시 `q` 키보드 누르기)

```bash
git show 커밋아이디
```

### 8. commit 내용 수정하기 (수정말고 덮어씌우는걸 추천)

- 바로 전 commit 내용 수정하기

```bash
git commit --amend
```

### 9. `GitHub의 온라인 주소 연결`하기

- 등록하기

```bash
git remote add 별명 주소
git remote add origin https://github.com/wltjs6668/til_git.git
```

- 목록 보기

```bash
git remote -v
```

- 삭제하기

```bash
git remote remove 별명
git remote remove aaa
git remote -v
```

### 10. GitHub로 push 하기

```bash
git push -u 별명 현재 브랜치
git push -u origin main

git push //위의 명령과 같음
```

### 11. 최소 알아야하는 git 명령

```bash
git add .
git commit
git push
```

# Git 으로 브랜치 관리하기

## Branch 란?

- 개발에서 구현해야 하는 각각의 기능이 있습니다.
- 하나의 기능을 구현 완료하였다면, 소스를 버전으로 보관하는 것.
- 다음 기능을 구현한다면 새로운 소스 버전을 만들어서 진행하는 것.

## Branch 초기 이름 셋팅

```bash
git config --global init.defaultBranch main
```

## Branch 생성하는 법

```bash
git branch 브랜치명
git branch trip
```

## Branch 목록 보는 법

```bash
git branch
```

## 원하는 Branch 로 이동하기

```bash
git switch 브랜치명
git switch trip
```

## 원하는 Branch 삭제하는 법

```bash
git branch -d 브랜치명
git branch       //목록 필수 확인!
git switch main // 다른 브랜치로 이동

git branch -d trip //삭제 실습
```

## 작업이 완료되면 Branch 합치기

```bash
git merge 합치는 대상브랜치 이름
git merge trip
```

# Git commit 관리하기

## 1. 바로 이전 커밋 내용 수정하기

- 커밋을 실행 후 바로 내용을 수정하는 경우

```bash
git commit --amend 엔터

내용수정 진행 > 저장

git log --oneline 엔터
```

## 2. 오래전 커밋 내용 수정하기(권장하지 않음.)

- 협업에서 문제 발생 소지
- 커밋 히스토리를 통해서 `해시값` 알아보기

```bash
git log --oneline 엔터
```

```bash
ex)
$ git log --oneline
d1c3309 (HEAD -> main, origin/main) [docs] 브랜치의 이해
b69b523 [docs] 깃허브 기본 사용 및 연결법
189efb5 [docs] 깃허브 명령어를 공부하고 있음.
bd3256d [커밋타입] 커밋 타이틀
fea3e3b 깃허브 사용법 정리중
```

- 해시값 파악 후 실행(^ 기호는 시작 이라는 뜻.)

```bash
git rebase -i 해시값^ 엔터
```

```bash
ex)
git rebase -i fea3e3b^
```

```bash
ex)
pick bd3256d [커밋타입] 커밋 타이틀
pick 189efb5 [docs] 깃허브 명령어를 공부하고 있음.
pick b69b523 [docs] 깃허브 기본 사용 및 연결법
pick d1c3309 [docs] 브랜치의 이해
pick 8459f84 진행중
```

- 위 처럼 나온 곳에서 `pick` 을 `eidt`으로 수정 후 저장

```bash
ex)
pick bd3256d [커밋타입] 커밋 타이틀
eidt 189efb5 [docs] 깃허브 명령어를 공부하고 있음.  !!! 수정
pick b69b523 [docs] 깃허브 기본 사용 및 연결법
pick d1c3309 [docs] 브랜치의 이해
pick 8459f84 진행중
```

- 실제 내용 수정

```bash
git commit --amend 엔터

수정 및 저장
```

- 마무리해서 main으로 이동하기

```bash
git rebase --continue
```

## 3. 깃허브에 commit 수정 내용 반영하기

### 3.1. 바로 커밋 수정 후 바로 push하기

### 3.2. 이전 커밋 수정 후 push하기
