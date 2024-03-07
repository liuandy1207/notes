# Git Basics

`git` is a source code management system. 

## Key Terms
- **Repository** <br>
  → the location of the main/canonical version of the code <br>
- **Working Directory** <br>
  → a copy of the repo where changes are made first (before saving them to the repo) <br>
- **Staging Area** <br>
  → a collection of related changes (changeset) from the working directory that will be committed as a single change to the repo <br>

## Initialization - `git init`
Places a directory under `git` version control.

## Tracking Files
```git
git status      // show differences between the repo, working directory, and staging area

git add FILES   // places an untracked file in the staging area


```

## Committing Staged Changes
```git
git commit -m "COMMIT_MESSAGE"

```


