## Data Type - `int`
- 32-bit, 4 bytes
- Range: $-2^{31}$ to $2^{31}-1$
  
Values outside of the range results in **overflow**.

## Data Type - `char`
- 8-bit, 1 byte
- Range: $-128$ to $127$

Typically used to store ASCII characters (indicated by single qutoes `'`). <br>

<img width="745" alt="Screenshot 2024-02-06 at 11 17 46 AM" src="https://github.com/liuandy1207/notes/assets/72530429/d5ea6968-b052-494c-b4c9-ba8509a847f4">

## Data Type - `float`
- 32-bit, 4 bytes

Susceptible to accumulating precision errors. `double` has better precision, but is still inexact. 
  
```C
float pi = 3.14159f;   // f-suffix defines floats

```
