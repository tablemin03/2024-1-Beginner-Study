## Fork
* 다른 사용자의 Repository를 자신의 계정으로 복사하여 독립적으로 수정하고 관리
' Git Hub의 오픈소스 프로젝트에 참여할 수 있음 '

## Star
* 관심 있는 Repository나 프로젝트에 star를 달아 "북마크"와 같이 관리

## Issue
* Repository에서 작업 계획, 토론 및 추적을 위해 활용

## Branch
* 기존 브랜치에서 분기되어 생성되는 별도의 작업 공간
* fork와 달리 같은 Repository에 생성됨
### Branch Naming Convention
/// "type/<issue 번호>-<간략한 설명>"

## Pull Request
* 분기된 Branch를 다시 병합하기 위한 절차
* 새로운 변경을 제안하거나 병합 시 발생하는 충돌을 해결
* Merge에 앞서 코드 리뷰

## Merge (Merge에는 3가지 옵션이 존재)
### Merge Commit

    * 두 브랜치를 공통 부모로 하는 새로운 commit 'E'를 만듦
    * A, B, C의 커밋이 그대로 main 브랜치로 병합

### Squash and Merge (과제 기준)

    * A, B, C의 커밋을 'squash' -> 하나의 커밋으로 main 브랜치로 병합

### Rebase and Merge (초심자 이용 X)

    * A, B, C 커밋의 base를 재설정
    * 모두 새로운 커밋으로 변경 (원래 Feature에 있던 commit을 main으로)
    * commit hash가 변경됨
    * 무수한 충돌을 경험할 수 있으니 사용에 주의

## Commit Id
    * commit의 식별을 위해 사용하는 40자 길이의 16진수
    * 중복 확률은 2의 80제곱 분의 1 (아주 간혹 가능)
    * SHA-1 해시 함수를 사용