# Git Cheatsheet

> A handy list of commonly used Git commands.

## Commands

### Initialise

```sh
$ git init
$ git remote add origin https://github.com/foo/bar.git
```

### Clone

```sh
$ git clone https://github.com/foo/bar.git
```

### Branch

```sh
# List all branches
$ git branch

# Create a new branch
$ git branch hotfix

# Switch to a branch
$ git checkout hotfix

# Create a new branch, and switch to it
$ git checkout -b hotfix

# Delete a local branch
$ git branch -D hotfix

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
# View changes made to a file
$ git diff foo

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
$ git checkout foo

# Discard changes to all files
$ git checkout -- .

# Delete all untracked files
$ git clean -df
```

### Syncing with remote

```sh
# Sync with the remote branch
$ git fetch

# Sync with the remote branch, and merge it into the local branch
$ git pull
```

### Tag

```sh
# List all tags
$ git tag

# Tag a commit
$ git tag -a v1.0.0 ea506f6c2c -m '1.0.0'

# Push tags
$ git push --tags origin master
```

### Staging

```sh
# Stage a modified or untracked file
$ git add foo

# Stage a deleted file
$ git rm foo

# Stage all modified and untracked files (ignores deleted files)
$ git add .

# Stage all modified and deleted files (ignores untracked files)
$ git add -u

# Unstage a single file
$ git reset -- foo

# Unstage all files
$ git reset -- .
```

### Commit

```sh
# List commit history
$ git log

# Make a commit
$ git commit -m 'foo'

# Amend the last commit message
$ git commit --amend -m 'bar'

# Amend the last commit message after having done a `git push`
$ git commit --amend -m 'bar'
$ git push origin +master

# Delete the last commit
$ git reset --soft HEAD~1

# Delete the last commit, and unstage all files
$ git reset --soft HEAD~1
$ git reset -- .

# Delete the last commit after having done a `git push`
$ git reset --soft HEAD~1
$ git push origin +master

# Merge multiple commits (eg. the last 3 commits) into one
$ git rebase -i HEAD~3
# 1. Mark all commits other than the first with `squash`, then save and quit.
# 2. Enter a new commit message, then save and quit.
```

### Push

```sh
# Push changes
$ git push origin master

# Push changes, overriding the remote
$ git push origin +master
```

## Aliases

Put the following in your `~/.bashrc` or `~/.bash_profile`:

```sh
alias g='git'
alias ga='git add'
alias gb='git branch'
alias gc='git commit'
alias gcm='git commit --amend -m'
alias gcl='git clone'
alias gco='git checkout'
alias gd='git diff'
alias gdc='git diff --cached'
alias gf='git fetch'
alias gi='git init'
alias gl='git log'
alias gm='git merge'
alias gp='git push'
alias gpl='git pull'
alias gpo='git push origin'
alias gpod='git push origin dev'
alias gpoh='git push origin hotfix'
alias gpom='git push origin master'
alias gr='git reset'
alias grao='git remote add origin'
alias grm='git rm'
alias gs='git status'
alias gu='git reset --soft HEAD^ && git reset .'
```
