# git CLI 연습

## git commands

- $ git status
- $ git add
- $ git commit -m "Input user's some message"
- $ git log
  - $ git log --graph --all --oneline
- [$ git branch](git_branch)
- [$ git merge 브랜치명](git_merge)


```bash

$ git add .

```

현제 디렉토리의 모든 파일을 add 하라는 명령이 됨
. : 현재 디렉토리를 나타냄. 이 와이드카드를 사용하면 현제 디렉토리의 모든 파일을 add 하라는 명령이 됨

커밋 메세지를 작성하지 않고 commit을 했을 경우
- 바로 vi에디터가 열리게 된다. 이때 당황하지 않고
- : (콜론)을 타이핑 한다. 
- 넣고 싶은 메세지를 넣고 키보드의 esc 키를 누르면 작성이 끝난다
- :wq를 입력하면 메세지 입력이 모두 끝난다

## git branch

- 브랜치 생성 : $ git branch 브랜치명
- 브랜치 확인
  - 기본 : $ git branch (위치한 브랜치에 * 표시 되어있다.)
  - 상세 : $ git branch -v
- 브랜치 이동 : $ git checkout 브랜치명

## git merge

- $ git merge 브랜치명 --no-ff
- vi에디터가 실행된다. (당황하지 않고) esc키를 누르고 :wq를 누른다.

### conflict

동일한 파일의 동일한 위치에 여러 변경사항을 병합하려는 경우 발생

- 현재 브랜치의 내용 : <<<<<<< HEAD 부터 ======= 까지
- 땡겨 오는 브랜치의 내용 : ======= 부터 >>>>>>> merge-conflict

### merge 취소

$ git merge --abort

## git stash

- 작업 일시 중지, 작업 중이던 내용이 임시 저장된다.
- untracking 파일은 적용 되지 않는다. 즉 임시저장 되지 않는다.
- 목록 보기 : $ git stash list (모든 브랜치의 stash가 나온다)
- 이름 부여 : $ git stash save "stash명"
- 꺼내기
  - $ git stash pop (잘라내기)
  - $ git stash apply stash@{2} (복사하기)
- 삭제
  - 특정 : $ git stash drop stash@{1}
  - 모두 : $ git stash clear

stash는 스택 구조 FILO (맨 먼저 생성된 stash가 제일 마지막에 나온다)
맨 위의 stash도 삭제 않고 꺼내기 바랄 때는 apply를 사용한다