# C Strings

There is NO BUILT-IN STRING type in C. <br>
The convention is that a C string is an ARRAY OF `char`s, terminated by the null-character (`'\0'`). <br>

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

