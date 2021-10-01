## git flow process

### Initialization

```bash
git flow init
```

- command for git flow init
- After execute this command, you can set branch naming convetion.(Recommanded default value)


### Develop new feature
```bash
git flow feature start MY_FEATURE
```

- make new branch for new feature.
- new branch name: feature/MY_FEATURE

```bash
git flow feature fininsh MY_FEATURE
```

- after develop new feature, merge feature branch to develop branch
- change this branch  to develop branch.
- merge feature branch to develop branch.
- remove feature branch.

### release

```bash
git flow release start VERSION
```
- make new release branch.
- change current branch to release branch

```bash
git flow release finish VERSION
```

- write release note and tags.
- merge release branch to main branch and develop branch.
- change current branch to develop branch.
- remove release branch.

### summary
```bash
git flow init
git flow feature start MY_FEATURE
git flow feature finish MY_FEATURE
git flow release start VERSION
git flow release finish VERSION
git push origin --tags
```
---
# CH2. revert
## 1. rename
- `mv`로 이름을 바꾸거나 이동을 시켰을 때

- mv를 하면 현재 위치의 file을 삭제 후, 새 파일을 생성하기 때문
	- 이 경우, 다시 원래 이름으로  되돌리거나, 이동시키면 됨
	- 왜냐하면, 이전 상태와 가장 마지막 상태만 비교하기 때문에 ! (이름이 같아져서 비교할 때는 이전과 같은 상태가 되어서 상관없음)

- 단순히 이동을 시켰지만  원래있던 파일의 history가 깨짐

#### 🙆‍♀️ 해결방법 : `$ git mv FILENAME`

## 2. undoing
- 변경사항이 마음에 안 들 때 (한 번에 되돌리기도 가능)

#### 🙆‍♀️ 해결방법 : `$ git checkout -- FILENAME`
	- ( $ git restore -- FILENAME ) 동일함
#### 🙆‍♀️ 해결방법2 : `$ git checkout -- .`
	- (모든 file에 대해 작업)

## 3. unstaging
- 올라갔을 때 다시 취소 (add 취소)
	- add 이후 commit 이전
#### 🙆‍♀️ 해결방법 : `$ git reset HEAD FILENAME`
#### 🙆‍♀️ 해결방법 : `$ git rm -f FILENAME`

## 4. modify commit
#### `$ git log` 로 stage에 올라간 commit을 확인할 수 있음

- 가장 최근의 commit 만 수정
#### 🙆‍♀️ 해결방법 : `$ git commit --amend`

## 5. cancel commit
#### 🙆‍♀️ 해결방법 : `$ git revert --no-commit HEAD~3..` 	
	- 최근부터 3개를 뒤로 돌리겠다(삭제함)
	- --no-commit : 원래 취소하면 취소commit message가 찍히는데 그걸 안 찍겠다는 말
- `$ git commit`
	- 다시 취소했음을 알려주어야 함
- `$ git push`
