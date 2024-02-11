## Locations & Navigation

```bash
/          # root directory
~          # home directory
~USERID    # USERID's home directory
.          # current directory
..         # parent directory

pwd               # print full path to the working directory
cd [DIRECTORY]    # change directory
```

## Commands
Embedded commands get executed first in an expression. After execution, their value in the expression is replaced by the commands output.

```bash
man [COMMAND]       # show command manual

$([COMMAND_EXPRESSION])    # embedded command

ctrl + a            # go to the beginning of the line
ctrl + e            # go to the end of the line
option + ←          # jump word left
option + →          # jump word right
ctrl + l            # clear screen (by scrolling down)

```

## Permissions
File permissions can be viewed by using `ls -l`. 

![image](https://github.com/liuandy1207/notes/assets/72530429/8095f10b-fa26-499e-9b00-78bb798a8ad4)
![image](https://github.com/liuandy1207/notes/assets/72530429/da874e9c-f5d3-4fc2-9b8a-f79a84e4f93f)

For directories

```bash
r    # read permission granted
w    # write permission granted
x    # execute permission granted
-    # permission NOT granted

```


## Files
```shell
# LIST
ls      # list all non-hidden files
ls -a   # list all files, including hidden files
ls -l   # list in long format

# READ
cat [FILES]                    # concatenate file(s) and print to stdout
head [FILES]                   # outputs the first 10 lines of each file
head -n [NUMBER] [FILES]           # outputs the first NUMBER lines of each file
wc [FILES]                     # print line / word / byte counts for each file
echo "[EXPRESSION]"            # print [EXPRESSION] to stdout

# ORDERING
sort [FILE]                    # sort the lines of files
sort -u [FILES]                    # suppress duplicates when sorting
shuf [FILES]                   # output each line from the files in random order
shuf -n [NUMBER] [FILES]           # output NUMBER lines in random order

# CREATE
mkdir DIRECTORY    # create directory
touch FILE         # create empty file, if FILE does not already exist
zip NAME PATH      # create a zip file named NAME

# COPY
cp [SOURCE/FILE] [DESTINATION/FILE]    # create a copy of the source at destination
mv [SOURCE/FILE DESTINATION/FILE]      # move source to destination or rename (if source = destiation)

# DELETE
rm [FILE]            # remove file
rm -r [DIRECTORY]    # remove directory (and all files inside)
```

## Redirection & Pipes
```bash
< [FILE]   # redirects the contents of FILE into stdin
> [FILE]   # redirects the output of stdout into FILE
2> [FILE]  # redirects the output of stderr into FILE
&> [FILE]  # redirects the output of stdout and stderr into FILE
>>         # concatenate, instead of overwriting

> /dev/null    # output directed to this location will be discarded

[COMMAND1] | [COMMAND2]    # take the stdout of one command and make it the stdin of another command

```

## Find & Globbing
```bash
?        # single wildcard character
*        # any amount of wildcard characters
[SET]    # one character from SET
[!SET]   # one character NOT from SET

find [EXPRESSION]    # search for files in a file hierarchy

```

## `egrep`
```bash
egrep "[PATTERNS]" [FILES]      # output lines that match a pattern
egrep -i "[PATTERNS]" [FILES]   # ignore case distinctions

# PATTERN COMPONENTS / REGULAR EXPRESSIONS
"^abc"         # the pattern must exist at the start of the line
"abc$"         # line must end with the pattern
"abc"|"cba"    # "or"
"."            # any single character
"[abc]"        # any single character from the set
"[abc]{n}"     # n characters from the set
"[^abc]"       # any single character NOT from the set
# escape special characters with \

"abc"*         # preceding subexpression can be repeated 0 or more times
"abc"+         # preceding subexpression can be repeated 1 or more times
"abc"?         # preceding subexpression can be repeated 0 or 1 times

```









