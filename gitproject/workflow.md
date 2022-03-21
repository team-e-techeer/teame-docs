# Git Workflow

- 새 프로젝트의 경우, 로컬 컴퓨터에서 작업하기 위해 clone 해줌

  ```
  git clone <project url>
  ```

- 모든 기능 분기는 프로젝트의 최신 코드 상태에서 생성

  ```
  git checkout main
  git fetch origin
  git reset --hard origin/main
  ```

  혹은

  ```
  git pull origin main
  ```

- 새 기능을 개발하기에 앞서 격리된 작업 브랜치를 만들고, 해당 브랜치로 체크아웃 한다.

  ```
  git checkout -b <branchname>
  ```

  혹은

  ```
  git branch <branchname>
  git checkout <branchname>
  ```

- issue 확인 및 해당 작업 진행

  ```
  git add <file1> <file2> ...
  git commit -m "commit message"
  ```

- 원격 branch에 푸시

  ```
  git push -u origin <branchname>
  ```

- Github 저장소에서 Compare & Pull Request 버튼을 통해 Pull Request 생성

- PR 요청은 검토자가 코드 변경내역을 확인하고 Merge 여부를 결정

- Merge 이후 동기화 및 branch를 제거

reference

- https://github.com/elsewhencode/project-guidelines#git-workflow
- https://wayhome25.github.io/git/2017/07/08/git-first-pull-request-story/
