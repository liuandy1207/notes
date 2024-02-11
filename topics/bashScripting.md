## `bash` Shell Scripts
`bash` shell scripts are plain text files that contain a sequence of `bash` shell commands. <br>

When execute permissions are given, scripts can be exeucted through a direct path. <br>
Otherwise, scripts can be executed through `bash [FILENAME]`. <br>

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









