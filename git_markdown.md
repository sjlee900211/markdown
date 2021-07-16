# Git

(**버전**을 통해) 코드 관리 도구

* 버전 관리 도구
  * 변경 이력 트래킹
  * 언제든 특정 시점으로 이동 가능
* 백업 도구
* 협업 도구



# SCM & VCS

* SCM: Source Code Management (소스 코드 관리)
* VCS: Version Control System (버전 관리 시스템)



### 1.1 버전관리

* 버전 간의 차이점을 손쉽게 볼 수 있다.



### 1.2 백업

* 여러 대의 컴퓨터를 동기화시킬 수 있다.
* push <-> pull



### 1.3 협업

* 원격 저장소를 매개로 push & pull로 협업할 수 있다.



# Git 버전관리

> 중요: Git은 **폴더 단위**로 코드 관리

* 커밋== 버전 생성==스냅샷 촬영==현재 상태 저장



# `git init`

특정 폴더를 git으로 관리 시작

* `(master)` 프롬프트에 표시
* `.git` 폴더 생성
  * `.git` 폴더 삭제 시 git 관리 중지



# `git status`

git에게 상태 확인

* `git init`직후

``` 
On branch master: master 라고 하는 branch에 있어

No commits yet: 아직 commit 없어

nothing to commit (create/copy files and use "git add" to track)
: commit 할 게 없어 (트래킹 하고 싶으면 `git add` 명령어를 사용해)
```

* `a.txt` 파일 생성 직후

```
Untracked files: 추적되지 않은 파일이 있어
  (use "git add <file>..." to include in what will be committed)
        a.txt (빨강)
   commit 될 수 있게 포함하고 싶으면 `git add <파일명>`을 사용해
   
nothing added to commit but untracked files present (use "git add" to track)        

```



* `git add a.txt`직후

```
Changes to be committed: commit될 변경 사항이 있어
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt (초록)
```



# `git add [파일명]`

Staging Area(스냅샷 무대)에 파일 추가




# `git commit -m "커밋 메시지"`

버전을 생성

* 커밋(버전) 구성 요소
  * 해시(Hash)
  * 작성자
  * 날짜
  * 커밋메시지: 버전에 대한 설명

```
[master (root-commit) c244c22] First commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 a.txt
```



# `git log`

버전(커밋)들의 히스토리(로그)



# `git config`

설정

* `git config [설정할 내용] [설정할 값]`
  * `git config user.name 'Celine Lee'`
  * `git config user.email 'sjlee900211@gmail.com'`
  * `git config --global`: 전역 설정



```
Author identity unknown: 작자 미상

*** Please tell me who you are.: 니가 누군지 말해주세요.

Run 다음을 실행하세요

	git config --global user.email "you@example.com"
	git config --global user.name "Your Name"
	
to set your account's default identity.
Omit --global to set the identity only in this repository.
```



# 백업

1. 원격 저장소 생성
2. remote 정보 입력
3. git push



# `git remote`

* 등록된 remote 저장소 이름을 보여준다.

  ```
  $ git remote
  origin
  ```



# `git remote -v`

* 등록된 저장소 이름과 URL을 표시한다.

  ```
  $ git remote -v
  origin  https://github.com/sjlee900211/first.git (fetch)
  origin  https://github.com/sjlee900211/first.git (push)
  ```



# 	`git remote add [remote name] [location]`

* 새로운 remote를 추가한다. [location]에는 URL 또는 파일 경로를 넣을 수 있다.

  ```
  $ git remote add origin https://github.com/sjlee900211/markdown.git
  ```



# `git push origin master`

* origin이라는 저장소의  master branch에 밀어넣는다.

# `git remote show [remote name]`
* 어떤 이름을 갖고 있는 remote의 branch와 정보를 표시한다.
  ```
  $ git remote show origin

  * remote origin
  Fetch URL: https://github.com/sjlee900211/markdown.git
  Push  URL: https://github.com/sjlee900211/markdown.git
  HEAD branch: master
  Remote branch:
    master tracked
  Local ref configured for 'git push':
    master pushes to master (up to date)

# `git remote rm [remote name]`
* remote 경로를 제거한다.

# `code`
* Visual Studio Code를 열어라.
* 현재 CMD 경로에서의 VS Code를 열고 싶을 경우 `$ code .`