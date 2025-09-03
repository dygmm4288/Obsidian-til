---
title: "2025-08-30 GIT REBASE"
date: "2025-08-30"
status: in-progress
---

## 배운 것
- `git rebase`는 브랜치의 기반(base)를 다른 커밋으로 옮겨서 히스토리를 "다시 쌓는" 명령어이다.
- 어떤 브랜치의 변경 사항을 새로운 기준(commit base)위에 붙여 마치 거기서부터 시작한 것처럼 만드는 행위.
### 예시
#### 현재상황
```mathematica
main: A---B---C
            \
feature:     D---E
```
#### rebase 실행
git rebase main
```mathematica
main: A---B---C
	            \
feature:         D`---E`
```
- D\` , E\`는 동일한 작업이지만, 새로운 부모 커밋(C)를 기준으로 다시 만들어진 커밋이다.

### 장점
- 히스토리가 일직선으로 형성돼 마치 브랜치 없이, 순서대로 개발한 것처럼 보인다.
- 불필요한 merge commit을 줄인ㄷ나.
### 단점
- 히스토리를 재작성하기 때문에, 이미 원격에 올라간 커밋을 rebae하면 충돌 발생
- 협업 중인 브랜치는 merge를 쓰는게 안전
### 명령어 종류
- `git rebase <branch`: 브랜치 기반 옮기기
- `git rebase -i <commit>`: interactive rebase -> 커밋 수정, 합치기, 삭제 가능
- `git pull --rebase` 원격 브랜치를 가져올 때 merge 대신 rebase해서 합치기
## 다음 할 일
- 