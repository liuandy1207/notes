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
```bash
man [COMMAND]       # show command manual

# embedded comand
$([COMMAND_EXPRESSION])        # gets executed first in an expression, then replaced by its output in the expression

ctrl + l            # clear screen (by scrolling down)

```

## Files
```bash
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

## Redirection 
```bash
< [FILE]   # redirects the contents of FILE into stdin
> [FILE]   # redirects the output of stdout into FILE
2> [FILE]  # redirects the output of stderr into FILE
&> [FILE]  # redirects the output of stdout and stderr into FILE
>>         # concatenate, instead of overwriting

> /dev/null    # output directed to this location will be discarded

|          # take the stdout of one command and make it the stdin of another command

```

## Find & Globbing
```bash
?        # single wildcard character
*        # any amount of wildcard characters
[SET]    # one character from SET
[!SET]   # one character NOT from SET

find [EXPRESSION]    # search for files in a file hierarchy

```
