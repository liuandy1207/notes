# C Primitive Data
C uses a **STATIC TYPING** system where:
- All types **MUST BE KNOWN** when the file **COMPILES**, and
- The type of an identifier **CANNOT CHANGE**. 

## Integers - `int`
32-bits of data are interpreted as integers. <br>
`int`s can have values between $-2^{31}$ and $2^{31}-1$. 

### Octal
`int` values that start with `0` are evaluated in octal. 

### Hexadecimal
`int` values that start with `0x` are evaluated in hexadecimal. 

## Bool - `bool`
32-bits of data interpreted as **BINARY FALSE** (`0`) or **TRUE** (any other value).

## Characters - `char`
8-bits of data are interpreted as an ASCII character. <br>
`char`s can have values between $-2^8$ and $2^8$. <br>
Single quotes are used to indicate an ASCII character. <br>
`\0` is the **NULL** character.
<img width="909" alt="Screenshot 2024-03-02 at 7 42 39 PM" src="https://github.com/liuandy1207/notes/assets/72530429/8172d3f9-8449-4405-b2c7-b6a799ee8185">

## Floating Point Numbers - `float`
32-bits of data are interpreted as a floating point number. <br>
`float`s are susceptible to accumulating precision errors. 
```C
float pi = 3.14159f    // f suffix to define floats

```

### Double Precision Floating Point Numbers - `double`
64-bits of data are interpreted as a double floating point number. <br>
`double`s are more signficantly more precise than `float`s, but are still inexact and susceptible to error. 
