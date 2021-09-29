# Git

> 분산버전관리시스템

## git 저장소 만들기

```bash
$ git init
Initialized empty Git repository in C:/Users/student/Desktop/test/.git/

(master) $
```

* `.git` 폴더가 생성되며, 버전이 관리되는 저장소
* git bash에서는 `(master)` 로 브랜치가 표기 된다.

## 버전 만들기

### `add`

> Working directory 상의 변경 내용을 staging area 에 추가하기 위해 사용

```bash
$ git add <파일/폴더/디렉토리>
$ git add . # 현재 디렉토리 변경 모두
$ git add a.txt   # 특정 파일
$ git add folder/ # 특정 폴더 
$ git add *.png   # 특정 확장자
```

#### 예시

```bash
$ touch a.txt
$ git status
On branch master

No commits yet
# 트래킹되지 않는 파일 / Working directory
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        a.txt

nothing added to commit but untracked files present (use "git add" to track)
$ git add a.txt
$ git status
On branch master

No commits yet
# 커밋될 변경사항들!!! (Staging area)
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt

```

### `commit` 

> Staged 상태의 파일들을 커밋을 통해 버전으로 기록

```bash
kimsubeen@gimsubin-ui-MacBookAir first % git commit -m 'add hello'
[master 5b393fd] add hello
 1 file changed, 1 insertion(+)
```

- SHA-1 해시를 사용하여 40자 길이의 체크섬을 생성하고, 이를 통해 고유한 커밋을 표기
- 커밋 메시지는 변경사항을 나타낼 수 있도록 명확하게 작성해야 함
- Git은 데이터를 파일 시스템의 스냅샷으로 관리하고 매우 크기가 작음
- 파일이 달라지지 않으면 성능을 위해 파일늘 새로 저장하지 않음
- 기존의 델타 기반 버전 관리시스템과 가장 큰 차이를 가짐

## 상태 관련 명령어

### `status`

> Git 저장소에 있는 파일의 상태를 확인하기 위하여 활용

```bash
kimsubeen@gimsubin-ui-MacBookAir first % git status
On branch master
nothing to commit, working tree clean
```

- 파일의 상태를 알 수 있음
  - Untracked files
  - Changes not staged for commit
  - Changes to be committed
  - Nothing to commit, working tree clean

### `log`

> 현재 저장소에 기록된 커밋을 조회, 다양한 옵션을 통해 로그를 조회할 수 있음

```bash
kimsubeen@gimsubin-ui-MacBookAir first % git log
commit 5b393fdf2bed5d2ec79a03f35938fa22f8d37800 (HEAD -> master)
Author: subeen-me <subeen.me@gmail.com>
Date:   Wed Sep 29 15:16:49 2021 +0900

    add hello

commit 0945d2c52d4afe5bbb929a02fd335cc25d70b1cf
Author: subeen-me <subeen.me@gmail.com>
Date:   Wed Sep 29 15:05:53 2021 +0900

    First commit
```





맥일땐 cd 하고 폴더를 끌어오면 된다

