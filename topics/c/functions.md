# C Functions

## Assertion Function - `assert(EXPRESSION)`
Terminates the program if `EXPRESSION` yields `0` (false). <br>
Otherwise, continues to the next line of code. <br>

It is good style to assert requirements. 

## Text Output Function - `printf("FORMAT_STRING")`
Produces text output. 
```C
printf("Hello World!");
printf("This is an integer: %d", 1);

```

### Format Specifiers
Format specifiers act as a placeholder for non-`String` additional arguments to be supplemented. 
```C
%d    // int
%c    // char

```

### Special Characters
```C
\n    // newline character
%%    // % character
\\    // \ character
\"    // " character
\'    // ' character

```
