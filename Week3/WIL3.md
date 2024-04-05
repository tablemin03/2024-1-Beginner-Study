## Pull Request (복습)
- 분기된 Branch를 다시 병합하기 위한 절차
- 새로운 변경을 제안하거나 병합 시 발생하는 충돌을 해결
- Merge에 앞서 코드 리뷰

## git log
- commit 기록을 최신 순으로 확인
- --oneline 옵션을 사용하면 각 커밋을 한 줄에 요약

## Commit Id
- commit의 식별을 위해 사용하는 40자 길이의 16진수
- 중복 확률은 2의 80제곱 분의 1
- SHA-1 해시 함수를 사용

## HEAD
- HEAD는 **현재 작업 중인 위치**를 가리킨다
- 현재 작업중인 브랜치의 가장 최근 commit
- 다음 commit의 base가 되는 commit
- 새로운 commit이 생기면 HEAD도 변경

## git status
- 세 가지 상태에 따라 파일을 분류하여 확인

# commit 되돌리기
## commit --amend
- 마지막 commit의 내용에 변경이 있을 때 사용
- 완전히 새로운 commit으로 대체
    - commit id가 바뀜
- vim으로 진입하여 commit 메시지를 수정하게 됨
    '-m' option으로 vim 진입 없이 commit 메시지 수정하기
    $ git commit --amend -m "커밋 메시지"

    '--no-edit' option으로 commit 메시지 수정 없이 commit 수정
    $ git commit --amend --no-edit

**혼자 사용하는 공간에선 사용해도 되지만 다른 사람과 작업하는 공간에서는 사용하면 안됨. - 다른 사람이 작업 기반으로 하고 있는 commit은 amend X (commit id가 아예 바뀌기 때문)**

## reset
- commit을 제거하는데 사용
- 3가지 옵션 존재
    - *soft, mixed(default), hard*
- 돌아갈 commit의 id를 사용
    $ git reset '--option' "<commit id>"
    ex) $ git reset --soft a1s2d3f

### reset --soft
- commit만 취소
- 변경 사항이 staging area로 감
### reset --mixed
- 커밋을 취소
- 변경 사항이 working directory로 돌아감
### reset --hard
- 커밋을 취소
- 변경 사항을 모두 제거하고 이전 커밋으로 돌아감
*5번째까지 커밋이 있을 때, 돌아갈 커밋이 3번째 커밋이라면 4~5번째 커밋이 취소됨*

### 추가
- git reset .
    - Staging Area에 add된 내용을 삭제하는 명령어다. 이때 작업했던 Working Directory(파일 ,내용들)는 삭제되지 않는다. 실수로 git add를 해서 Staging Area에 의도대로 올라가지 않았을 때 꽤 자주 사용하게 되는 명령이다.

## revert
- commit을 제거하지 않고 되돌림
- 되돌리기 위한 새로운 commit이 생성됨
- --edit 옵션이 default
    ex) $ git revert a1s2d3f
### revert --no-edit
- 편집기(vim) 진입 없이 바로 revert 가능
    $ git revert --no-edit "<commit id>"
### revert --no-commit
- 직접 commit 하지 않고, revert 내용을 Staging Area에 올림

## reset vs revert
- reset은 commit을 삭제하므로 위험
- commit을 공유하는 다른 브랜치에도 영향을 줄 수 있음
- commit을 삭제하기보다 생성하여 되돌리는 revert가 안전
- revert를 사용하면 중간에 무슨 문제가 있었는지, 왜 돌아갔는지 등의 기록이 가능하고, 다른 사람들과 같은 브랜치에서 함께 작업할 때 코드 충돌을 최소화할 수 있다.
- reset을 사용하면 커밋 히스토리를 깔끔하게 유지할 수 있고, 혼자 작업할 때 편하게 되돌아갈 수 있다는 장점이 있다.