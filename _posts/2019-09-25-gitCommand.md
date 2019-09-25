---
layout: post
title: "Git Basic Command"
---

# Git Basic Command

## Git Basic Logic
1. Git Bash 실행
2. 로컬 저장소로 사용할 디렉터리로 이동한다.
```
$ cd 이동경로
```
3. 해당 디렉터리를 git 설정한다.
```
$ git init
```
4. 임의의 파일 추가하고 변경한다.
5. 변경 사항을 확인한다.
```
$ git status
```
6. 확인된 변경 사항을 Stage로 올린다.
```
$ git add test.txt
```
7. Commit 한다.
```
$ git commit -m "add test"
$ git commit -am "add test"
```
8. 원격지로 push한다.
```
$ git push
$ git push -u origin master (처음 push하는 경우 브랜치가 생성되지 않아, master 브랜치를 생성하면서 push한다.)
```
9. 원격지로 가서 push된 내용을 확인한다.

## Git Command
기본 설정 관련
* user name을 설정한다.
```
$ git config --global user.name "test"
```
* user email을 설정한다.
```
$ git config --global user.email "test@test.co.kr"
```
* 설정 내용을 확인한다.
```
$ git config --list 
```

remote 관련
* 원격지 주소를 간단하게 설정한다.
```
$ git remote add (별명) (원격지 주소)
```
* 설정한 원격지를 확인한다.
```
$ git remote (설정명 출력)
$ git remote -v (설정명 원격지 주소까지 출력)
```
* 특정 원격지로 push 할 경우
```
$ git push (원격지명) (브랜치명)
```

Reset
* 선택한 commit 까지 초기화시킨다.
```
$ git reset --option (이동 할 Commit id) 
```
* --option
    * hard : 이동 Commit까지 완전 초기화
    * soft :   reset 대상 commit 내역이 stage에 올라가있는 상태 
    * mixed : reset 대상 commit 내역이 stage에 올라가지 않은 상태


### ETC
* 현재 위치 확인
```
$ pwd
```
* commit message 확인
```
$ git log
```
* git directory 상태 확인
```
$ git status
```
* 원격 directory clone
```
$ git clone (원격지 주소) 
```
* checkout : commit 내역이나, branch를 이동한다.
```
$ git checkout (이동할 commit id / 이동할 브랜치 명)
```

한글 깨질때 경우 
* 이미 원격지에 깨진채로 올라간 파일은 되돌릴 수 없음.
* 프로젝트  (.project)   파일encoding="UTF-8" 확인
* Eclipse > Window > Preference >> Encoding 변경전 기존 소스 한글 깨짐
```
General > Workspace > (하단 좌측) Text file encoding > Other 체크 > UTF-8 선택
General > Content Types > Java Clss File > (하단) Default encoding > UTF-8 입력
```