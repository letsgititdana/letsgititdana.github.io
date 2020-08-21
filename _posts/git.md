# Git 

> SCM (Source Code Management)  =  ''코드 관리 툴''
>
> VCS (Version Control System)  =  ''버전을 통한''



## Main Points

1. Git은 폴더 단위로 파일을 관리
2. 관리 관련 내용은 .git/ 폴더 안에 저장됨
3. git 상태 저장 == commit (사진찍기)
   1. 파일을 사진대 위에 올려놓기 == add (에 불과하다. commit을 최종적으로 해야지.)
   2. git status로 changes, untracked files 등 파악

```bash
$ git init
$ git status
$ git add markdown.md
$ git config --global user.email "ryudana@gmail.com"
$ git config --global user.name "Jiwon Yu"
$ git commit -m "first commit"
$ git log
$ git log --oneline

$ git diff --staged

$ git checkout (id)
```



## Github

> Local repository (~/git) --> Remote repository

```bash
$ git remote add 주소이름 주소URL
$ git remote add origin https://github.com/letsgititdana/gitbasic.git
$ git remote -v
origin  https://github.com/letsgititdana/gitbasic.git (fetch)
origin  https://github.com/letsgititdana/gitbasic.git (push)

$ git push origin master
```

- 주소이름을 보통 origin이라고 함. (왜?)



> Let's make campus <-> home environment through github

```bash
$ mkdir campus
$ cd campus
$ touch README.md
$ echo '# Homework' > README.md
$ cat README.md

# Step 1. Push (on the campus)
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git log
$ git remote add origin https://github.com/letsgititdana/home_environment.git
$ git remote -v
$ git push origin master

# Step 2. Clone (at home, for once)
$ git clone https://github.com/letsgititdana/home_environment.git
$ cd home_environment
$ echo '## Homework done' > README.md
$ git add README.md

# Step 3. Push (at home)
$ git commit -m "Update READ.md"
$ git push origin master

# Step 4. Pull (on the campus)
$ git pull origin master

# Step 5. push on campus -> pull at home -> push at home -> pull on campus -> ...
```



## Commit msg Conventions





## Exercise

> 1.  01_Github_ITL.pdf 마크다운으로 변경 -> 02_git.md
>
> 2.  ~/TIL 생성 00.md 01.md 02.md 저장
>
> 3.  github TIL 저장소 생성 후 push
>
> 4. home_environment 에서 TIL 저장소 clone 후, README.md 수정해보기

![git](git.jpg)