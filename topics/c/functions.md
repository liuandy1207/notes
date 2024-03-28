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
&emsp; → Time: $O(n)$, when given a STRING ($n$ is the length of the string)

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



\\ read in string (stop when whitespace or EOF)
char name[10];
int arr_len = 10;
scanf("%9s", name);    // the number between %s should be 1 less than arr_len - 1 (save a space for '\0')

```
&emsp; → Time: $O(n)$, when given a STRING ($n$ is the length of the string)

## String Length Function - `strlen(STRING)`
Returns the length of the given string. Length does NOT include the null-terminator. <br>

&emsp; → Time: $O(n)$ <br>
&emsp; &emsp; → avoid calling `strlen` within loops because of the time complexity


## String Compare Function - `strcmp(STRING1, STRING2)`
Returns a NEGATIVE value if STRING1 precedes STRING2. <br>
Returns a POSITIVE value if STRING2 precedes STRING1. <br>
Returns `0` if STRING1 and STRING2 are equal.

&emsp; → Time: $O(n)$, $n$ is the minimum length of STRING1 and STRING2

## String Copy Function - `strcpy(DEST, SRC)`
Copies the content of string DST into SRC. <br>
Note that DEST must be large enough (including space for `'\0'`. <br.
&emsp; → Time: $O(n)$, $n$ is the length of SRC

## String Concatenate Function - `strcat(DEST, SRC)`
Appends the content of string SRC onto DST. <br>
Note that DEST must be large enough (including space for `'\0'`. <br.
&emsp; → Time: $O(n)$, $n$ is the length of SRC

## Memory Allocation Function - `malloc(SIZE)`
Library: `<stdlib>`  <br>
Dynamically allocates memory from the heap memory section. <br>
Returns a pointer to the beginning of the block, or `NULL` if there was not enough heap memory available. <br>
Time: $O(1)$ <br>
Note: always use with `sizeof` to allocate enough memory to store a specific data type <br>
Note: the memory provided by `malloc` is UNINITIALIZED
Note: `malloc` returns a VOID POINTER (can point to any type)

## Memory Free Function - `free(PTR)`
Deallocates the space previously allocated by a memory allocation function. <br>
If `PTR` is `NULL`, this function does nothing. <br>
Note: every allocated memory block MUST be manually freed before the program terminates. <br>
Note: `free` does NOT mutate data, the data is still there, but its pointer is now invalid. <br>
Note: it is good form to assign `NULL` to a freed (dangling) pointer.

## String Duplication Function - `strdup(str_ptr)`
Duplicates a string and returns a different pointer. 

## Memory Reallocation Functino - `malloc(ptr, newsize)`
Returns of block of heap memory of size `newsize`. <br>
If `ptr` is not `NULL`, the content of `*ptr` will be copied over and `ptr` will be freed. <br>
Note: `realloc` is a `malloc`, a "copy", and then a `free` <br>
Time: O(n)














