<<<<<<< HEAD
# git flow - coworking

## 팀장의 역할
1. 새로운 repo를 생성
2. clone 진행
3. `git flow init`: branch 생성
4. 대상 파일 생성 (`touch git.md`)
5. `git add git.md`
6. `git commit`
7. `git push -u origin develop`

## 팀원의 역할
1. Repo 주소를 받는다
2. 팀원이 Issue를 작성한다
3. FORK를 해서 사본을 만든다
4. FORK한 repo의 주소로 clone을 진행한다 (`git clone [forked-repo]`) 
5. `git flow init`: branch 생성
6. Feature branch를 생성한다(`git flow feature start [branch-name]`)
7. 작업을 완료하고 `git add [file-name]`, `git commit`을 진행한다
8. 마지막 commit에서는 이슈가 마무리 되었음을 알리기 위해 resolve, close, fix과 넘버링된 이슈를 입력해준다(`Resolve #1`)
9. `Git flow feature finish [branch-name]`
10. Git push origin develop (첫 push인 경우 `-u`를 추가한다)
11. merge 이전에 수정이 요청된 경우 develop branch에서 수정하는 것이 좋다
=======
# CH2. revert
## 1. rename
- `mv`로 이름을 바꾸거나 이동을 시켰을 때

- mv를 하면 현재 위치의 file을 삭제 후, 새 파일을 생성하기 때문
	- 이 경우, 다시 원래 이름으로  되돌리거나, 이동시키면 됨
	- 왜냐하면, 이전 상태와 가장 마지막 상태만 비교하기 때문에 ! (이름이 같아져서 비교할 때는 이전과 같은 상태가 되어서 상관없음)

- 단순히 이동을 시켰지만  원래있던 파일의 history가 깨짐

#### 🙆‍♀️ 해결방법 : `$ git mv FILENAME`
>>>>>>> 53d11cfacfdfa3f2e45b5f387151d69db809310e
