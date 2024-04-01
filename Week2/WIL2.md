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
    "type/<issue 번호>-<간략한 설명>"

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


# 명령어 및 실습

## Branch
    현재 브랜치 확인하기
    $ git branch

    모든 브랜치 확인하기
    $ git branch -a
## Branch 생성/삭제
    브랜치 생성하기
    $ git branch "<브랜치 이름>"

    브랜치 삭제하기 
    $ git branch -D "<브랜치 이름>"
## Branch - checkout
    브랜치 이동하기
    $ git checkout "<브랜치 이름>"

    브랜치 생성 후 이동하기
    $ git checkout -b "<브랜치 이름>"

### 실습내용
    New issue를 만들고 새로운 브랜치를 만든다.

    새로운 브랜치에 파일을 푸시하고 main에 merge를 통해 병합한다.

### 실습하다가 찾아보며 배운 내용
파일을 수정하고 add 후 commit해도 계속 바뀌지를 않길래 어떤이유 에서인지 찾아보았다. ~~해결은 못함~~ 그 과정에서 pull에 대해서 조금 알게 되었다.

만약 local repository와 remote? 원격? repository의 내용이 다르면 충돌이 일어날 수 있는데, 그 때 쓰는게 **pull**이다.

애초에 왜 local과 GitHub의 내용이 다르냐 하면 GitHub의 repository에 들어가서 내용을 수정했을 수도 있는 것이고, 협업하는 과정에서 다른 사람이 commit 했을 수도 있다는 것 같다.

그 때 **pull**을 사용하면 GitHub와 local repository를 동기화 시켜서 같게 만들어준 후 내가 수정할 것을 수정하고 commit하면 충돌을 줄일 수 있다. ~~아마도~~

### 파일을 수정해도 add와 커밋을 하지 못했던 이유를 알게 되었고, 고난 끝에 과제를 성공했다. 

1. 일단 내가 꼬이게된 첫번째 이유인 커밋을 하지 못한 이유 - 파일 수정 후 저장을 누르지 않았기 때문이다. 저장을 해야지 파일이 수정된 것이 확인이 된다.
2. Pull request 실패 - 스쿼시 앤 머지가 생겨야 하는데 나는 생기지 않고 오류가 났다. 이 이유는 pull을 하지 않아서 생긴 것인데, 원격에서 내가 main 브랜치를 수정했고, 그 과정에서 local에서 push한 파일과의 충돌이 생겼다. 해결법은 충돌을 찾아 해결한 후 merge를 한다. 이후 pull을 통해 local에도 반영해주고, 이후에 다시 브랜치를 파서 파일을 스쿼시 앤 머지 해줬다.

### 느낀점
    이번 과제를 통해서 원치 않았던 방식으로 깃허브에 조금 익숙해졌는데, 아직도 어렵다는 생각이 든다. 일단 pull이 무지막지하게 중요하다는 생각이 들고, 계속 수정의 수정의 수정을 거듭하면서 계속 오류가 생겼기 때문에 어째서 branch를 파는건지 또한 알게됐다고 할 수 있다. ~~나도 알고싶지 않았어.~~

    **오늘의 교훈**

    다음부턴 꼭 pull을 애용하자 ^^


<https://github.com/tablemin03/2024-1-Beginner-Study/pull/4>