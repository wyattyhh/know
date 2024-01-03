---
layout: default
title: Git
parent: Dev
---

## Commit Style
feat：新功能（feature）
fix：修补bug
docs：文档（documentation）
style： 格式（不影响代码运行的变动）
refactor：重构（即不是新增功能，也不是修改bug的代码变动）
test：增加测试
chore：构建过程或辅助工具的变动

## Useful Commands
Staging hunk by hunk. ( one file can be staged separate)
```
git add -p
```
Stage certain type of file.
```
git add *.js
```
Add all changes and commit with message.
```
git commit -am "commit message"
```
Set the current branch to the preceding commit (undo commit)
```
git reset HEAD^
```
Adding `--soft` will keep those files in the _index_: (ready to be committed)
```
git reset --soft HEAD^
```
Adding `--hard` to discard all last commit's changes
```
git reset --hard HEAD^
```
Discard all unstaged changes
```
git resotre .
```
Stash
```
git stash
git stash pop
```
Revert certain commit (could be any specific commits)
```
git revert <commit hash>
```
Merge master to current branch
```
git merge master
```
Rebase master to current branch
```
git rebase master
```
Merge one commit to current branch
```
git cherry-pick <commit hash>
```
Interactive Rebase ([a guide](https://hackernoon.com/beginners-guide-to-interactive-rebasing-346a3f9c3a6d))
```
git rebase -i <commit hash>
```