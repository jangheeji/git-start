# Git 소개
- 소프트웨어 개발 과정에서 소스코드의 버전관리 담당

- 버전관리 VCS (Version Control System)
    - 파일의 변화를 시간에 따라 기록
    - 특정 시점의 버전을 나중에 꺼내올 수 있는 시스템
    - 프로젝트를 통째로 이전 상태로 되돌릴 수 있고
    - 현재 어떤 변경이 이루어졌는지 명확하게 이해

- 분산 버전 관리 시스템 (Distributed Version Control System)
    - 코드의 복사본이 개발자의 로컬 시스템 뿐만 아니라
    - 원격 서버에도 저장이 됨.
    - 복사본 로컬 저장소 클라이언트 아무데서나 서버를 복원할 수 있음.
    - Clone을 통해 데이터를 백업하거나 복제할 수 있음.
    - 중앙집중식 버전관리 Subversion(SVN)
        중앙의 서버에서 모든 파일의 변경 이력을 관리
    - Git은 분산버전관리시스템(DVCS를 사용)

- Git의 역할
    - 2005년에 Git이 탄생
    - 빠른 속도, 단순한구조, 완벽한 분산
    
    - 버전관리 및 복구 : 개발 과정 중대한 오류를 신속하게 복구
    - 협업 강화 : 여러 사람이 동시의 프로젝트를 할수 있도록 지원
    - 변경 추적 : 언제 누가 코드를 변경했는지 추적 및 원인 분석
    - 분산 환경 지원 : 로컬 또는 원격 저장소 사용하여 인터넷 끊긴 환경에서도 작업 가능

## Git 설치
- [깃 공식 홈페이지](https://git-scm.com/)
- 다운로드 받아 실행

* 주의사항
    - git 초기 브랜치 이름이 master -> main 으로 변경됨에 따라
    - git 설치시 main 선택을 하는 것이 좋다.

- Git Bash
    - 윈도우 운영체제에서 Git을 사용하기 위한 CLI(Command Line Interface)


## git 초기 설정

- Git 설치 후 개인 사용자 이름과 이메일 주소를 설정

```bash
# 사용자 이름 전역 설정
git config --global user.name "사용자이름"
# 이메일 전역 설정
git config --global user.email "이메일주소"
```

- 일반적으로 GitHub 의 사용자이름과 이메일주소를 사용.

```bash
# 설정 확인하기
git config --list
```

## Git 저장소 만들기

- Git 저장소를 만들기 원하는 폴더로 이동한 후

```bash
git init
```

- 명령어를 입력하면 해당 폴더(프로젝트 폴더) 기준으로
- `.git` 폴더가 생성되고, 해당 폴더에 모든 버전 정보와 필요한 메타데이터가 저장

- `.git` 폴더를 `로컬 저장소(Local Repository)` 라고 부름.

* 윈도우에서 Git Bash를 사용할 경우
    - 우클릭 > 새폴더 > '프로젝트폴더명' 생성
    - 해당 프로젝트폴더에서 우클릭하여 'Open Git BASH Here' 클릭하면
    - 해당 경로 위치로 Git Bash가 실행된다.

## Git 상태 확인하기

```bash
# Git 상태 확인
git status
```

```bash
On branch main      # 현재 브랜치는 main이다.

No commits yet      # 아직 커밋이 된 것이 없음

nothing to commit (create/copy files and use "git add" to track)
# 파일을 추가하거나 복사하여 git add하세요.
```

## Git 저장소에 파일을 추가하기
- 새로운 파일을 만들거나 복사하여 프로젝트 폴더 내에 추가

```bash
# 해당 파일을 스테이징 영역에 추가
git add 파일이름
```

- 스테이징 영역
  - Git에서 커밋할 변경사항을 준비하는 공간

- 깃 파일의 4가지 상태
    1. Untracked : Git이 파일을 추적하지 않고 있는 상태
    2. Tracked : Git이 파일을 추적하고 있는 상태
        1. Staged : 스테이징 영역에 파일이 추가됨 (git add 명령)
        2. Unmodified : 최신 커밋에서 내용이 변경되지 않은 상태
        3. Modified : 최신 커밋에서 내용이 변경된 상태

- 커밋(commit)
    - Git에서 변경 사항을 저장소에 영구적으로 기록하는 작업
    - 프로젝트의 특정 시점의 상태를 스냅샷으로 기록
    - 커밋은 고유한 해시값으로 식별
    - 커밋 메시지 등의 정보를 포함

```bash
# git 커밋하기 (커밋 메시지를 기록하지 않을 경우 기본 에디터가 열림)
git commit

# 커밋 기록 보기
git log
```

* vim 에디터
    - Unix, Linux 계열에서 주로 기본 에디터로 사용되는 명령줄 텍스트 편집기
    - 주요 특징
        - 모드 (mode)가 존재함.
        - 다양한 명령어와 간축키가 있음.
        - 플러그인 및 확장 기능 있음.
        - 키보드로만 작업을 수행 하고 마우스를 사용 하지않음.
    - 모드
        1. 명령 모드 9(Command Mode)
        - Vim 을 실핼 하면 기본적으로 들어가는 모드
        - 입력 모드로 전환 하려면 'i' 또는 'a'  등
        - 다양한 명령어가 실행 가능
        2. 입력 모드 (Input Mode)
          -텍스트를 직접 입력 할 수 있는 모드
            -명령 모드로 전환 하려면 'esc' zl
        3. 비주얼 모드 (Visual Mode)
    - 명령어
        - `:w` : 저장하기
        - `:q` : 종료하기
        - `:wq` : 저장하고 종료하기
        - `:!wq` : 저장하고 강제로 종료하기

        ## git 정리 (초기화부터 커밋까지)

        ```bash
    # 프로젝트 디렉토리 경로로 이동
        cd 경로명

     # git 저장소 초기화
        git init

     # 현재 프로젝트 경로에 있는 모든 파일을 스테이징 영역에 추가ㅁㅇ
        git add .

    # 커밋 메셎와 함께 커밋 생성
        git commit -m "커밋메세지"
        ```


    - 깃 상태 및 이력 조회
```bash
# 상태 확인
git status

# 이력 조회하기
git log
git log --oneline   # 커밋을 한 줄로 요약해서 보여줌
git log --oneline --graph  # 이력을 그래프로 보여줌

## git checkout (특정 커밋으로 체크아웃하기)

- 프로젝트 코드의 특정 버전으로 돌아가고 싶을 때
```bash
# 커밋 해시 확인
git log --oneline

# 특정 커밋 시점으로 되돌아가기
git checkout 커밋해시

# 예시
git checkout ale4fb5        # 커밋해시는 커밋마다 다름

# 체크아웃 이전으로 돌아가기
git checkout -

# 특정한 브랜치로 돌아가기
git checkout 브랜치이름

# 예) 메인 브랜치로 돌아가기
git checkout main
```
- 커밋해시 : 커밋의 고유한 식별 문자열, 너무 길기 때문에 앞 7자만 따서 사용함.
- git을 사용하여 특정시점으로 프로젝트를 자유롭게 이동할 수 있음


## Github를 통한 원격 저장소 관리
- 로컬 저장소 : Local Repository
    - 개인 컴퓨터에서 위치는 개인 작업 공간
- 원격 저장소 : Remote Repository
    - 공개적으로 소스를 공유하고 협업을 하기 위한 공간
    - Github 협업 플랫폼을 사용.

1. Github 계정 생성 및 로그인
2. 새 저장소를 생성
    - github 대시보드에서 "New Repository"
    - 저장소 이름, 설명, 공개여부 등을 설정
    - 만들어진 저장소의 원격주소를 확인
3. 로컬 저장소와 원격 저장소 연결하기
```bash
# 원격 저장소 추가
git remote add origin 원격저장소URL주소
# 로컬 저장소 변경사항을 원격저장소에 반영 (push)
git push -u origin main
```
    - 필요한 경우 github에 웹브라우저 로그인
4. 원격 저장소 내용을 로컬로 가져오기
```bash
# 가져오기(pull)
git pull origin main
```

### git remote
  - 원격 저장소 관리 명령
  
```bash
# 저장소 목록 간단한 출력
git remote
# 저장소 목록과 주소 보기
git remote -v
# 원격 저장소 추가하기 (일반적으로 원격저장소 이름 origin)
git remote add [원격저장소이름] [원격저장소주소]
# 원격 저장소 주소 변경하기
git remote set-url [원격저장소이름] [원격저장소주소]
# 원격 저장소 주소 삭제하기
git remote remove [원격저장소이름]

# 원격 저장소로 push하기 (일반적인 초기 브랜치 이름 main)
git push [원격저장소이름] [브랜치이름]
# 원격 저장소로 pull하기
git pull [원격저장소이름] [브랜치이름]
```

### push와 pull

 - git push [원격저장소이름] [브랜치이름]
 - 첫번째 push에서 -u 옵션을 사용
 - 해당 브랜치의 기본 원격 저장소와 브랜치를 설정
 - 예
 ```bash
 # 처음에 -u 옵션을 주면 기본값 설정
 git push -u origin main

 # 이후 push하게 될 경우 저장소명과 브랜치명 생략
 git push
 ```
 - 적절한 권한이 없는 경우 push 실패 가능
 - 로컬 저장소 브랜치가 원격 저장소 브랜치보다 뒤처져 있을 경우 실패 가능

 - git pull
   1. 원격 저장소에서 데이터를 가져오고
   2. 가져온 데이터를 현재 로컬 브랜치와 병합

   - `git pull origin main`
   
   - 주의사항
    - 로컬 변경사항과 원격 변경사항이 충돌할 경우, 충돌을 해결하고 병합 가능
    - 작업을 시작하기 전에 항상 최신 상태를 유지하기 위해 `git pull`을 자주 사용하는 것이 좋음 (협업을 할 때)

### README 파일

- `README.md` 프로젝트의 접점으로 프로젝트에 대한 중요 정보 제공 문서
- 일반적으로 프로젝트 이름, 설명, 설치방법, 환경설정, 사용예제, 라이선스 등을 담고 있음.
- Github 저장소에서 첫 페이지에서 마크다운 문법으로 확인 가능

### .gitignore
  - Git 버전관리에서 제외하고 싶은 파일이나 디렉터리가 있을 때
  - Git 추적에서 제외할 수 있음.
  - 임시파일, 비밀정보 등을 제거

### git clone (원격 저장소 복제)
- 원격 저장소의 복제본을 로컬 저장소에 생성하고 싶을 때 완전한 복사본을 로컬에 생성 가능

```bash
git clone [원격저장소주소]
```

- 현재 로컬 디렉토리 위치에서 저장소이름의 디렉토리가 생성


