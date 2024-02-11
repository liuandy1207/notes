## `bash` Shell Scripts
`bash` shell scripts are plain text files that contain a sequence of `bash` shell commands. <br>

When execute permissions are given, scripts can be exeucted through a direct path. <br>
Otherwise, scripts can be executed through `bash [FILENAME]`. <br>

By convention, these files end with `.sh`. <br>

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












