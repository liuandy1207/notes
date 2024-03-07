# Git Branches

In git, branches are mandatory. We are always working in one. <br>
By default, git creates a branch called `master` on the first commit. <br>
Another pointer that git creates is `HEAD`. <br>

`master` is a pointer to the latest commit. <br>
`head` is a pointer to the active branch.

## Creating New Branches
```git
git branch IDENTIFIER

git branch    // lists all existing branches, * indicates the active branch

```
Creates a new branch called `IDENTIFIER`. <br>
By default, this branch will point to whatever `HEAD` is pointing at (the active branch). <br>
Note: the new branch will contain the commits of the active branch

## Switching Branches
```git
git checkout BRANCH

```
Any changes made in one branch stay local to that branch until merged. 

## Merging Branches
```git
git merge BRANCH

```
Merge `BRANCH` into the active branch. <br>
When branches diverge (conflicting modifications), git automatically attempts to resolve the divergent history. <br>
However, this can fail and will require human intervention to fix. 




