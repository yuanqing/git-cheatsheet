# Git Cheatsheet

> A handy list of commonly used Git commands.

## Commands

### Create new or download existing repository

```sh
# Initialize a new repository
$ git init
$ git remote add origin https://github.com/foo/bar.git

# Download an existing remote repository
$ git clone https://github.com/foo/bar.git
```

### Sync local repository with remote

```sh
# Sync with the remote branch
$ git fetch

# Sync with the remote branch, and merge it into the local branch
$ git pull
```

### Branching

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

### Tagging

```sh
# List all tags
$ git tag

# Tag a commit
$ git tag -a v1.0.0 ea506f6c2c -m '1.0.0'

# Delete a tag
$ git tag -d v1.0.0
```

### Stage changes

```sh
# Stage a modified or untracked file
$ git add foo

# Stage a deleted file
$ git rm foo

# Stage all modified or untracked files, ignoring deleted files
$ git add .

# Stage all modified or deleted files, ignoring untracked files
$ git add -u
```

### Unstage changes

```sh
# Unstage a single file
$ git reset foo

# Unstage all files
$ git reset -- .

# Restore a single file from the last commit
$ git checkout foo

# Restore all files from the last commit
$ git checkout -- .

# Delete all untracked files
$ git clean -df
```

### Review changes

```sh
# See unstaged changes made to a single file
$ git diff foo

# See unstaged changes made to all files
$ git diff

# See staged changes made to all files
$ git diff --cached

# Compare the last and second-last commits
$ git diff HEAD^ HEAD
```

### Commit changes

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

### Push changes to remote

```sh
# Push changes
$ git push origin master

# Push changes, overriding the remote
$ git push origin +master

# Push tags
$ git push --tags origin master
```

## References

- [Oh Shit, Git!?!](https://ohshitgit.com/)
