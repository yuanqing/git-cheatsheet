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

## Review changes
```bash
# Compare modified files with the last commit
$ git diff

# Compare staged files with the last commit
$ git diff --cached

# See changes made in the last commit
$ git diff HEAD^ HEAD
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

# Stage a deleted file
$ git rm foo.js

# Stage all modified and untracked files (ignores deleted files)
$ git add .

# Stage all modified and deleted files (ignores untracked files)
$ git add -u

# Unstage a file
$ git reset foo.js

# Unstage all files
$ git reset *
```

## Commit
```bash
# List commit history
$ git log

# Make a commit
$ git commit -m 'foo'

# Undo the last commit
$ git reset --soft HEAD~1

# Amend the last commit message
$ git commit --amend -m 'bar'

# Amend the last commit message after push
$ git commit -m 'foo'
$ git push origin master
$ git commit --amend -m 'bar'
$ git push origin +master

# Delete the last commit (best to avoid)
$ git reset --soft HEAD~1
$ git push origin +master
$

# Merge multiple commits (eg. the last 3 commits) into one
$ git rebase -i HEAD~3
# 1. Mark all commits other than the first with `squash`, then save and quit.
# 2. Enter a new commit message, then save and quit.
```

## Push
```bash
$ git push origin master
```
