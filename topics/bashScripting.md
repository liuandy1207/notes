## `bash` Shell Scripts
`bash` shell scripts are plain text files that contain a sequence of `bash` shell commands. <br>

When execute permissions are given, scripts can be exeucted through a direct path. <br>
Otherwise, scripts can be executed through `bash FILENAME`. <br>

By convention, these files end with `.sh`. <br>
```bash
#!/bin/bash

# script goes here

```

## Shell Variables
The `bash` shell can store information as strings and uses the same naming rules as `C`. <br>

```bash
x=1          # declare variable x
echo ${x}    # access and output variable x

```
Variable declaration cannot contain whitespace. If whitespace is in the desired value, surround with quotes. <br>

## Global Shell Variables
```bash
${PWD}          # present working directory, equivalent to executing pwd
${HOME}         # home directory, equivalent to ~
${SHELL}        # default shell
${PRINTER}      # default printer
${HOSTNAME}     # machine's name
${PATH}         # concatenation of all directories, seperated by :

```
`${PATH}` is the default search path for commands and programs.

## Command Line Arguments
```bash
${0}              # name of the current script
${1}, ${2}, ...   # argument 1, 2, ... of the current script
${#}              # number of arguments provided for the current script
${@}              # all provided arguments as seperate strings

shift    # discard the first argument and move all arguments one position to the left

```
## User Input
```bash
read VARIABLE									# reads user input and stores it in VARIABLE
read -p "PROMPT" VARIABLE 		# outputs PROMPT, reads user input, and stores it in VARIABLE
read													# reads user input and stores it in ${REPLY}

```
The default variable for `read` is `${REPLY}`.
## Conditional Operators
```bash
==, !=       # string equality and inequality
-eq, -ne     # integer equality and inequality
-gt, -ge     # integer > and >=
-lt, -le     # integer < and <=
!            # negation, can be used with other operators
-e           # file exists
-d           # file exists and is a directory
-f           # file exists and is a regular file
-r, -w, -x   # file exists and is readable/writeable/executable
-z           # check if length of a string is 0

&&           # and
||           # or

```

## Conditional Statements
```bash
test 1 -eq 1      # produces no output, but returns 0 in ${?} (true/success)
[ 1 -eq 1 ]       # same command as above, but different syntax (note the necessary whitespace)
exit NUM          # return an error code, use different numbers for different errors

# IF / ELIF / ELSE STATEMENTS
if [ CONDITION ]; then
  STATEMENTS
elif [ CONDITION ]; then
  STATEMENTS
else
  STATEMENTS
fi

```

## Loops
```bash
# WHILE LOOPS
while [ CONDITION ]; do
  STATEMENTS
done

# FOR LOOPS
for VARIABLE in SEQUENCE; do
  ${VARIABLE}      # changes every iteration to the next item in the sequence
  STATEMENTS
done

# EXAMPLE - while loop with changing variable
x=1
while [ $x -le $1 ]; do
  echo $x
  x=$((x+1))    # update integer variable through $(()) syntax, note the double brackets
done

```
A SEQUENCE is any list of items seperated by whitespace.
