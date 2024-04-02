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
- - dddd
- vim으로 진입하여 commit 메시지를 수정하게 됨
    '-m' option으로 vim 진입 없이 commit 메시지 수정하기

**혼자 사용하는 공간에선 사용해도 되지만 다른 사람과 작업하는 공간에서는 사용하면 안됨. (commit id가 아예 바뀌기 때문)**

## reset
- commit을 제거하는데 사용
- 3가지 옵션 존재
-   - *soft, mixed(default), hard*
- 돌아갈 commit의 id를 사용
    $ git reset '--option' "<commit id>"
// 필기 더

### reset --soft
- commit만 취소
- staging area로 감
### reset --mixed
### reset --hard

## revert
- commit을 제거하지 않고 되돌림
- 되돌리기 위한 새로운 commit이 생성됨
- --edit 옵션이 default
    ex) $ git revert a1s2d3f
    (제거한건 추가 추가한건 제거?)
