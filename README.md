# Git Cheatsheet

## Commands

### Initialise
```sh
$ git init
$ git remote add origin https://github.com/yuanqing/git-cheatsheet.git
```

### Clone
```sh
# Clone into current directory
$ git clone https://github.com/yuanqing/git-cheatsheet.git

# Clone into a specific directory
$ git clone https://github.com/yuanqing/git-cheatsheet.git foo
```

### Branch
```sh
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

### Review changes
```sh
# Compare modified files with the last commit
$ git diff

# Compare staged files with the last commit
$ git diff --cached

# Compare the last and second-last commits
$ git diff HEAD^ HEAD
```

### Discard changes
```sh
# Discard changes to a single file
$ git checkout foo.js

# Discard changes to all files
$ git checkout -- .

# Delete all untracked files
$ git clean -df
```

### Syncing
```sh
# Sync with the remote branch
$ git fetch

# Sync with the remote branch, and merge it into the current local branch
$ git pull

# Sync with a remote branch, discarding changes to all files in the current local branch
$ git fetch --all
$ git reset --hard origin/master
```

### Staging
```sh
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

### Commit
```sh
# List commit history
$ git log

# Make a commit
$ git commit -m 'foo'

# Amend the last commit message before a `git push`
$ git commit --amend -m 'bar'

# Amend the last commit message after a `git push`
$ git commit --amend -m 'bar'
$ git push origin +master

# Delete the last commit before a `git push`
$ git reset --soft HEAD~1

# Delete the last commit after a `git push`
$ git reset --soft HEAD~1
$ git push origin +master

# Merge multiple commits (eg. the last 3 commits) into one
$ git rebase -i HEAD~3
# 1. Mark all commits other than the first with `squash`, then save and quit.
# 2. Enter a new commit message, then save and quit.
```

### Push
```sh
$ git push origin master
```
