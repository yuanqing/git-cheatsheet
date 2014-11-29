# Git Cheatsheet

## Initialise
```bash
$ git init
$ git remote add origin https://github.com/yuanqing/git-cheatsheet.git
```

## Clone
```bash
# Clone into current directory
$ git clone https://github.com/yuanqing/git-cheatsheet.git

# Clone into a specific directory
$ git clone https://github.com/yuanqing/git-cheatsheet.git foo
```

## Branch
```bash
# List all branches
$ git branch

# Create a new branch
$ git branch hotfix

# Create a new branch, and switch to it
$ git checkout -b hotfix

# Switch to a branch
$ git checkout hotfix

# Delete a local branch
$ git branch -d hotfix

# Delete a remote branch
$ git push origin :hotfix

# Merge one branch into another
$ git checkout master
$ git merge hotfix

# Merge one branch into another as a single commit
$ git checkout master
$ git merge --squash hotfix
```

## Discard changes
```bash
# Discard changes to a single file
$ git checkout foo.js

# Discard changes to all files
$ git checkout -- .

# Delete all untracked files
$ git clean -df

# Sync with a remote branch, discarding changes to all files
$ git fetch --all
$ git reset --hard origin/master
```

## Staging
```bash
# Stage a modified or untracked file
$ git add foo.js

# Stage all modified and untracked files (ignores deleted files)
$ git add .

# Stage all modified and deleted files (ignores untracked files)
$ git add -u

# Stage a deleted file
$ git rm foo.js

# Unstage a file
$ git reset foo.js
```

## Commit
```bash
# List commit history
$ git log

# Make a commit
$ git commit -m 'foo'

# Amend the last commit message
$ git commit --amend -m 'bar'

# Merge multiple commits into one
$ git rebase -i HEAD~3
# 1. Mark all commits other than the first with `squash`, then save and quit.
# 2. Enter a new commit message, then save and quit.
```

## Push
```bash
$ git push origin master
```
