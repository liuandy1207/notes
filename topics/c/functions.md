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
&emsp; → Time: $O(n), when given a STRING ($n$ is the length of the string)

### Format Specifiers
Format specifiers act as a placeholder for non-`String` additional arguments to be supplemented. 
```C
%d    // int
%c    // char
%f    // float
%p    // hexadecimal address
%s    // string

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
char in_char = '\0';
int count = scanf("%c", &in_char);
\\ read in one character, excluding whitespace
int count = scanf(" %c", &in_char);

```

## String Length Function - strlen(STRING)
Returns the length of the given string. Length does NOT include the null-terminator. <br>

&emsp; → Time: $O(n)$ <br>
&emsp; &emsp; → avoid calling `strlen` within loops because of the time complexity


## String Compare Function - strcmp(STRING1, STRING2)
Returns a NEGATIVE value if STRING1 precedes STRING2. <br>
Returns a POSITIVE value if STRING2 precedes STRING1. <br>
Returns `0` if STRING1 and STRING2 are equal.

&emsp; → Time: $O(n)$, $n$ is the minimum length of STRING1 and STRING2












