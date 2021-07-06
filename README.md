# GitTips
Some use full tips for git

How to change last commit massage :
```sh
git commit --amend -m "New message"
```

How to add author name and email in commit massage :
```sh
git commit --amend --author "John <John@xyz.com>"
```

How to cherry pick without commit massage :
```sh
git cherry-pick {commitId} --no-commit
```

Interactive rebase for multiple commit squash with single commit:
```sh
git rebase -i --preserve-merges {commitId}
pick : main 
f : commit -1
f : commit -2
f : commit -3
:wq
:q!
git push -f origin {branch name}
```

Rebase child branch with parent:
```sh
git pull (Switch parent branch and take pull) ex : develop
Switch back your branch. ex : feature/One
git rebase develop (Rebase with develop : feature/One to develop)
git rebase --continue //optional if conflicts occur
git push -f
```

How to add file in git stash with stage file :
```sh
git stash save -u <name_of_stash>
```
Creating the stash as a patch :
```sh
git stash show "stash@{0}" -p > changes.patch
```
Applying the patch :
```sh
git apply changes.patch
```
Reverse the patch :
```sh
git apply changes.patch --reverse
```
