# 파일을 관리하기 위해서 git을 사용한다.
* 어떤 파일이 누가 언제 어떻게 수정되었는지를 추적하기 위해

# 버전관리 후 협업을 위해서 GitHub를 씀
## push를 통해 local에서 Remote로 이동

	Github에서 프로젝트를 공유하며 협업가능

# GitHub에서는 이런 것도 가능하다
* 이슈 트래킹
* 코드 리뷰
* GitHub Projects로 프로젝트 업무 관리
* Github Actions로 CI/CD
* 자세한 내용은 docs.github.com


# Git 최초 설정

	$ git config --global user.name "<깃허브 이름>"
	$ git config --global user.email "<깃허브 이메일>"



# git으로 파일 관리하기
1. 디렉토리에 git 저장소를 만들기

	a. git init

2. git으로 관리할 대상 등록하기

	a. git add

3. 파일 수정 후 로컬 저장소로 옮기기

	a. git commit

## .git 폴더를 만들어 디렉토리를 Git 저장소로 만들기

	$ git init

## 반대로 git으로 관리를 그만하고 싶다면?

	$ rm -r .git

## 모든 파일 한번에 등록

	$ git add .

## 하나씩 등록

	$ git add <파일명>

## unstage로 되돌리기

	$ git rm --cached <file>

## 파일 수정 후 로컬 저장소로 옮기기

	git commit

## Git에 커밋하기

	git commit -m "<commit message>"

# GitHub에 올리기에 앞서

	$ git remote add origin <주소>

	$ git branch -M main

	$ git push -u origin main

# Github에 올리기 

	$ git add <파일명>

	$ git commit -m "commit message"

	$ git push origin main

<https://github.com/tablemin03/tablemin03/tree/main/tablemin03>