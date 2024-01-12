
# TIL_StartCampDat2_240111

## Git : 분산 버전 관리 시스템

## 1. 개요
- **창시자**:  리누스 토르발스
- **개념**:  작업자의 소스코드를 분산 환경에서의 버전관리를 자동화
- **Git의 역할**:  ```$git init``` 한 로컬 저장소의 소스코드, 변경 및 수정 이력, 최신 여부, 시간, 작업자 정보 관리
<br><br><br><br>

## 2. 분산 환경에서 버전관리 필요한 이유?
- 여러 사람과 협업 할 때 분산 환경에서 작업자들간 충돌을 줄여 개발 생산성 향상
- 중앙 관리 서버의 장애나 손실에 대비하여 백업과 복구가 용이
- 인터넷 연결되지 않은 환경에서 로컬 저장소에서 작업 후 동기화 가능
<br><br><br><br>

## 3. Git의 3가지 영역
#### ⓐ **Working Directory(작업영역)**
```$git init```

실제 작업 중인 파일들이 위치하는 영역으로 git 버전관리 대상이 되는 디렉토리에 명령어 입력
#### ⓑ **Staging Area(저장 준비 영역)**
```$git add```

Staging Area에 파일을 등록하며, 등록된 파일만 commit 가능
  > commit : '버전'의 변경을 저장하는 행위

#### ⓒ **Local Repository(저장소)**
```$git commit ```

Staging Are에 놓인 파일을 로컬 저장소에 기록
<br><br>
![이미지2](image2.png)
<br><br><br>

## 4. 실습 해보기

### 1) git.config에 유저 정보 등록
```git
$ git config -global user.email 'email@abc.com'
$ git config -global user.name 'my name is name'
```
pc 사용자가 바뀌면 해당 정보를 초기화 해야 함을 유의

<br>

### 2) $git init

working directory로 지정하려는 경로에서 ```$git init``` 명령어를 통해 git 저장소를 초기화
#### ① ```$touch sample.txt```
연습을 위한 임의의 txt 파일 생성
#### ② ```$git status```

git 관점에서 현재 working stage와 staging area의 버전 상태 정보 조회

> **💡git init 주의사항**<br>**1. home directory, Desktop(바탕화면)에 ```$git init``` 금지**<br>**2. git 로컬 저장소 내에 또 다른 git 로컬 저장소를 만들지 말 것**<br>즉, 이미 git 로컬 자장소인 디릭토리 내부 하단에서 git 이닛 명령어 다시 입력하지 말 것

<br>

### 3) $git add FileName
```git
$git add sample.txt
```
- 변경사항 있는 파일을 staging ara로 등록하는 명령어

  staging area에 등록된 파일만 commit 가능<br>
- working directory 내 모든 파일을 stage로 올리려면```$git add .```
- ```$git add``` 명령 수행 전 후를 비교하기 위해 ```$touch test.txt```와 ```$git status```명령어로 확인해보기
<br>

### 4) $git commit -m 'commit msg'
```git
$git commit -m 'first commit'
```
- staging area에 있는 파일을 local repository에 기록하는 명령
- 이 때 반드시 '커밋 메시지'를 남겨야 함(버전 이름, 커밋 종류 등)
<br>

### 5) $git log
- ```$ git log ``` 커밋 내역 확인하는 명령어

  commit 에 대한 헤시값, 최신상태, 작업자, 커밋 시기, 커밋 메시지 정보 확인
- ```$ git log --oneline```
    깃로그를 한 줄로 짧게 요약
    
<br><br>

## 5. 참고
- 파일 수정 삭제 등 변경사항을 commit 하려면 항상 stage에 올리고 commit 해야 변경 이력이 남는다.
- commit 하지 않은 변경사항이 발생하면 해당 파일명이 초록색으로 표시되며 'U' 표기가 붙는다.
- commit 한 파일 내용을 수정하면 해당 파일명이 오렌지 색으로 표시되며 'M' 표기가 붙는다.
