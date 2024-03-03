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
%f    // float
%p    // hexadecimal address

```

### Special Characters
```C
\n    // newline character
%%    // % character
\\    // \ character
\"    // " character
\'    // ' character

```

## Text Input Function - `scanf("FORMAT_STRING", STORAGE_ADDRESS)`
Returns the number of successfully read values or the constant `EOF` to indicate that the end of a file has been reached. 
```C
\\ continuously read in integers
int input = 0;
while (scanf("%d", &input) == 1) {
  \\ ...
}

\\ read in one character, including whitespace
int count = scanf("%c", &in_char);
\\ read in one character, excluding whitespace
int count = scanf(" %c", &in_char);

```


