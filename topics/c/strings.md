# C Strings

There is NO BUILT-IN STRING type in C. <br>
The convention is that a C string is an ARRAY OF `char`s, terminated by the null-character (`'\0'`). 

Strings behave like arrays: their content is mutable, but their identifier is NOT reassignable. 

## String Initialization
```C
char str[4] = {'1', '2', '3', '\0'};   // length 7
char str[4] = "123";                   // length 7
char str[] = "cs136";                  // length 7

// this one is NOT a string (not null-terminated)
char ch_arr[6] = "CS 136"    // length 6

```

## Null Termination
Since strings are null-terminated arrays, their length does NOT need to be explictly tracked. <br>
Instead, the end of a string is indicated by the null-terminator. 

Side Note: it is good style to have `const` parameters to communicate that the string does not mutate. 

## Lexicographical Order
<img width="615" alt="Screenshot 2024-03-19 at 1 58 18 PM" src="https://github.com/liuandy1207/notes/assets/72530429/d025cca7-e1e8-4e94-b35c-b66f216b0634">
&emsp; → empty precedes any
&emsp; → uppercase precedes lowercase
&emsp; → if a match is made, compare the next character

## String Literals
Strings that are NOT initialized as arrays are STRING LITERALS. 

For string literals, the null-terminated `const char[]` is created in the GLOBAL READ-ONLY section of memory. <br>
when the string literal appears in the code, it is replaced by the address of this array. 

The content of string literal is IMMUTABLE, but their identifer is reassignable. 
