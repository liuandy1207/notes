# Git Basics

`git` is a source code management system. 

## Key Terms
- **Repository** <br>
  → the location of the main/canonical version of the code <br>
- **Working Directory** <br>
  → a copy of the repo where changes are made first (before saving them to the repo) <br>
- **Staging Area** <br>
  → a collection of related changes (changeset) from the working directory that will be committed as a single change to the repo <br>

## Basic Commands

### Initialization
```bash
git init

```
Places a directory under `git` version control. <br>
This is now the working directory.

### Staging Files
```git
git add FILES

git rm FILES    // inverse of git add, removes files from the WD and SA

```
Places an untracked file from the working directory in the staging area. 

### Committing Staged Changes
```git
git commit -m "COMMIT_MESSAGE"

```
Commits the changeset to the repo. 

### Monitoring Status
```git
git status

```
Show differences between the SA and the WD and between the SA and the repo. <br>
Also shows untracked files. 

### Viewing Commit History
```git
git log

```
Show commit history. 

### Comparing Modifications
```git
git diff

git diff --color-words    // color codes the resulting output for ease of reference

```
If no files has been staged, then it shows differences between the current WD and last commit. <br>
If files have been staged, then it shows differences between the current WD and the code at time of staging. 



