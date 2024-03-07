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
```git
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

## Undo Commands

### Revert
```git
git revert ID

git revert -n ID    // does not automatically commit the revert, allowing for more changes

```
Reverts a commit, given the commit's `ID` found by running `git log`.

### Reset
```git
git reset ID

git reset --hard
git rest --soft 

git reset     // defaults to reset to the last commit

```
Resets `HEAD` and the branch reference to a specified commit. <br>
Staging area will be cleared, but still available in the WD. <br>

`--hard` deletes the changeset and all modified files in the WD (even unstaged) will be reset to the time of the commit. <br>
`--soft` does not clear the staging area. Only modifies `HEAD` and the branch reference. 

### Checkout 
```git
// Usage on commits
git checkout ID

// Usage on files
git checkout ID;  -- FILE

```
When used on commits, git will load a snapshot of the repo at the time of the specified commit. <br>
When this occurs, `HEAD` will get DETATCHED. In this state, any changes made (even commits) do NOT affect the repo. <br>
If the intent is to undo changes, a new branch must be created to attatch `HEAD` onto. <br>
Any future work will branch off from this new branch. This is acceptable if the old branch is no longer needed. <br> 

When used on files, git will load a snapshot of a specific file at the time of the specified commit. <br> 
Additionally, providing a file does not detatch `HEAD`, so these checked out files can simply be committed to undo any changes. 











