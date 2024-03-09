# C Preprocessor Directives
When C files are compiled, the compiler runs a program called the PREPROCESSOR. <br>
The preprocessor looks for PREPROCESSOR DIRECTIVES in all of the provided C files. <br>
Preprocessor directives begin with a hashtag (#) and have a variety of uses. 

## `#include` Statements
```C
#include <stdio.h>          // <> for standard library files
#include "HEADER_FILE"      // "" for files located in the current source file directory

```
The preprocessor replaces the `#include` statement with the contents of the specified file. 

## Macro Expansion
```C
#define IDENTIFIER VALUE    // definition of an object-like macro

```

