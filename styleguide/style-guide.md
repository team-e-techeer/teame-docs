# Git Style Guide

## 1. Branches

#### Perform work in a feature branch.

- main
- feat/\*

### 1.1 main

> 제품으로 출시될 수 있는 브랜치
> 버전관리가 필요되는 경우 master/1.0.0 이러한 형식으로 브랜치를 생성합니다.

### 1.2 feat/\*

> 기능을 개발하는 브랜치 \*에는 이슈 단위로 브랜치 생성

### 1.3 상세 규칙

- main 브랜치는 feat/\* 브랜치에 의해 merge 되어 수정되야 합니다.
- feature 브랜치에서 main 브랜치에 merge 할 때,
  반드시 main 브랜치에 있는 내용을 pull 해야 합니다.
  (충돌시 로컬에서 수정하기 위해서)

## 2. Commits

#### Writing good commit messages

### 2.1 구조

`issue(옵션 ex MP-3) type(옵션): subject(필수)

body(옵션)`

- issue: 관련된 이슈 번호를 작성합니다.
- type: 어떤 의도로 커밋했는지를 type에 명시합니다.
- subject: 최대 50글자가 넘지 않도록 하고 마침표는 찍지 않습니다.
  영문으로 표기하는 경우 동사(원형)을 가장 앞에 두고 첫글자는 대문자로 표기합니다.
- body: 긴 설명이 필요한 경우에 작성합니다.
  한줄에 최대 75글자를 넘기지 않도록 합니다.
  어떻게 했는지가 아니라, 무엇을 왜 했는지 작성합니다.

  > commit 단위는 에러 안나는 최소 기능 기준으로

### 2.2 Type

Type은 항상 영문 소문자로 작성합니다.

- feat : 새로운 기능 추가
- fix : 버그 수정
- docs : 문서의 수정
- style : UI를 추가/변경 하거나 스타일 관련 수정
- refactor : 코드를 리펙토링
- test : Test 관련한 코드의 추가, 수정
- chore : 기능/테스트, 문서, 스타일, 리팩토링 외에 배포, 빌드와 같이 프로젝트의 기타 작업들에 대해 추가/수정

### 2.3 예제

`feat: Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.`

## 3. Pull Request (Merge)

### 3.1 규칙

- main 브랜치로의 merge는 feature/\* 브랜치에 의해서만 가능합니다.
- merge시 merge가 되는 브랜치에서 pull을 먼저하고 충돌이 있다면 해결한 뒤 merge를 해야 합니다.
- merge는 github pull request에서 진행합니다.

### 3.2 Conflicts

Merge 하는 두 브랜치에서 같은 파일의 한 부분을 동시에 수정하고 Merge 하면 Git은 해당 부분을 Merge 하지 못하게 됩니다.

Git은 충돌이 난 부분을 표준 형식에 따라 표시해줍니다.
그러면 개발자는 해당 부분을 수동으로 해결해야 합니다.

======= 위쪽의 내용은 HEAD 버전(merge 명령을 실행할 때 작업하던 master 브랜치)의 내용이고
아래쪽은 develop 브랜치의 내용입니다.
충돌을 해결하려면 위쪽이나 아래쪽 내용 중에서 고르거나 새로 작성하여 Merge 해야 합니다.

충돌난 부분을 모두 수정 후 git add명령으로 마무리하면 충돌이 해결됩니다.

reference

- [https://github.com/ikaruce/git-style-guide/blob/master/README.md](https://github.com/ikaruce/git-style-guide/blob/master/README.md)
- [https://git-scm.com/book/ko/v2](https://git-scm.com/book/ko/v2)
