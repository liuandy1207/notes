## `git help`
Displays a help manual for a given command.
```git
git help COMMAND

```

## `git init`
Place the current directory under Git version control. <br>
Automatically creates a hidden `.git` directory.

## `git add`
Add files from the working directory to the changeset. Begins tracking.
```git
git add FILE

```

## `git rm`
Remove `FILE` from the working directory. 
```git
git rm FILE

;  equivalent to 
rm FILE
git add FILE

```

## `git mv`
Move or rename `FILE`. Renaming occurs when the location is the same.


## `git commit`
Save the changeset to the local repository.
```git
git commit -m "MESSAGE"

```

## `git status`
List differences between staging area (working directory) and the repo. 

## `git log`
Show list of all previous commits. 

## `git diff`
If files were modified but were not staged (`git add`ed_, then show differences between current working directory and last commit. <br>
If files were modified and staged, then show differences between between staged files and the current working directory.

## `git clean`
```git
; show untracked files
git clean -n

; removes untracked files
git clean -f

```


## `git push` and `git pull`
Synchronize local and remote repositories.

