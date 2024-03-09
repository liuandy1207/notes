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
&emsp; → `IDENTIFIER` must NOT have any white space <br>
&emsp; → `IDENTIFIER` should be in all caps <br>
&emsp; → `VALUE` may have white space <br>
&emsp; → `VALUE` can be nothing (defaults to the empty string) <br>

The preprocessor replaces all instances of `IDENTIFIER` with `VALUE`. <br>

Constants can be defined by macros, but `const` is typically used instead. <br>
The exception is when an array of a constant length is defined. <br>
Using `const` creates an undesired variable length array, but using macros allows us to achieve the desired effect without creating a VLA. 

### Stacked Macro Expansion
The value of a macro can be a subsequent macro, creating a macro chain. 

## Conditional Compilation
```C
#if
  // ...
#elif
  // ...
#else
  // ...
#endif



// sends to compiler if MACRO is defined
#ifdef MACRO
  // ...
#endif

// sends to compiler if MACRO is NOT defined
#ifndef MACRO
  // ...
#endif

```
The preprocessor sends the embedded code to the compiler if the conditions are satsified. Otherwise, the code is supressed. 

### clang Command Line
```shell
clang -DMACRO -DMACROTWO=10 CFILE.c
# note the spacing of -D and MACRO

```
&emsp; → if a macro defined with `-D` is not given a value, its value will default to `1` <br>

The clang compiler will define `MACRO` when attempting to compile `CFILE.c`.

### Commenting Out Code
```C
#if 0
  // the surrounding code can be used to comment out segments of code
#endif

```
&emsp; → `#if` and `#endif` nest perfectly, as opposed to `/* */`

### `#include` Guards
```C
#ifndef UNIQUE_MACRO

#define UNIQUE_MACRO
#include UNIQUE_HEADER

#endif

```
Applying include guards in this style for ALL HEADER FILES prevents including the same header twice and undesired redefinitions. 
