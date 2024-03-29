# Command Line Basics

## Locations & Navigation
```bash
/          # root directory
~          # home directory
~USERID    # USERID's home directory
.          # current directory
..         # parent directory

pwd               # print full path to the working directory
cd DIRECTORY      # change directory
```

## Keyboard Shortcuts
```bash
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

```bash
r    # read permission granted
w    # write permission granted
x    # execute permission granted
-    # permission NOT granted
u    # owner/user
g    # group
o    # other
a    # all

chmod u+r THING     # add read permission for user
chmod u-r THING     # revoke read permission for user
chmod u=r THING     # set permission to r-- for user

```
For directories, execute permission allows entrance into the directory, but files may NOT be visible. <br>
Three [0-7] digits can be used to specify permissions. Each digit represents `rwx` in binary for each of `u/g/o`.

## Commands & Embedded Commands
Embedded commands return values to be used as arguments for another command. 
```bash
man COMMAND        # show manual for COMMAND

$(COMMAND_EXPRESSION)  # embedded command syntax, $()

```

## Files
```shell
# LIST (for directories)
ls      # list all non-hidden files
ls -a   # list all files, including hidden files
ls -l   # list in long format

# READ
cat FILES                      # concatenate file(s) and print to stdout
head FILES                     # outputs the first 10 lines of each file
head -n NUMBER FILES           # outputs the first NUMBER lines of each file
wc FILES                       # print line / word / byte counts for each file
echo "EXPRESSIOn"              # print EXPRESSION to stdout, quotes to preserve whitespace

# ORDERING
sort FILES                     # sort the lines of the files
sort -u FILES                  # suppress duplicates when sorting
shuf FILES                     # output each line from the files in random order
shuf -n NUMBER FILES           # output NUMBER lines in random order

# CREATE
mkdir DIRECTORY    # create directory titled DIRECTORY
touch FILE         # if FILE does not already exist, create an empty file titled FILE
zip ZIP PATHS      # create a zip file titled ZIP
unzip ZIP          # unzip zip file ZIP

# COPY
cp SOURCE/FILE DESTINATION/FILE      # create a copy of the source at destination
mv SOURCE/FILE DESTINATION/FILE      # move source to destination or rename (if SOURCE = DESTINATION)

# DELETE
rm FILE              # remove file
rm -r DIRECTORY      # remove directory (and all files inside)
```

## Redirection & Pipes
```bash
&          # stdout
&2         # stderr

< FILE     # redirects the contents of FILE into stdin
> FILE     # redirects the output of stdout into FILE
2> FILE    # redirects the output of stderr into FILE
&> FILE    # redirects the output of stdout *and* stderr into FILE

>>             # concatenate, instead of overwriting
/dev/null      # output directed to this location will be discarded

COMMAND1 | COMMAND2    # take the stdout of one command and make it the stdin of another command

```

## Find & Globbing
```bash
find EXPRESSION    # search for files in a file hierarchy

?        # single wildcard character
*        # any amount of wildcard characters
[abc]    # one character from the set abc
[!abc]   # one character NOT from the set abc

```

## `egrep`
```bash
egrep "REG_EX" FILES            # output lines that match a pattern
egrep -i "REG_EX" FILES         # ignore case distinctions

# REGULAR EXPRESSIONS
"^abc"         # the pattern must exist at the start of the line
"abc$"         # line must end with the pattern
"abc"|"cba"    # pattern abc or pattern cba
"."            # any single character
"[abc]"        # any single character from the set abc
"[abc]{n}"     # n characters from the set abc
"[^abc]"       # any single character NOT from the set abc

"abc"*         # preceding subexpression can be repeated 0 or more times
"abc"+         # preceding subexpression can be repeated 1 or more times
"abc"?         # preceding subexpression can be repeated 0 or 1 times

```
Using double quotes around regular expressions is recommended. <br>
Escape special characters with `\`.




