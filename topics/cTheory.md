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

Susceptible to accumulating **precision errors**. `double` has better precision, but is still inexact. 
  
```C
float pi = 3.14159f;   // f-suffix defines floats

```
## Data Type - `struct`
```C
// the declaration occurs outside of any functions
struct STRUCT_IDENTIFIER {
  TYPE FIELD1;
  TYPE FIELD2;
  ...
};     // notice closing semicolon

// notice inclusion of keyword struct
struct STRUCT_IDENTIFIER INSTANCE = {VALUE1, VALUE2, ...}; 

// intialize without ordering fields, any ommitted fields are automatically 0
struct STRUCT_IDENTIFIER INSTANCE = {.FIELD2 = VALUE 2};



// EXAMPLE: declaration and assignment
struct posn {
  int x;
  int y;
};

// {} can only be used for initialzation, it cannot be used for assignment later
struct posn p = {1, 2};
struct posn q = {3, 4};

p = q;   // copies all fields from q

```
NOTE: comparators and `printf` do NOT work with structures. You must define your own. <br>

No memory is reserved when a structure is declared. Memory is only reserved **at definition**. <br>
The required memory for a `struct` depends on the **order of the fields** because C will reserve extra space to **enforce alignment**. <br>

<img width="420" alt="Screenshot 2024-02-06 at 11 52 41 AM" src="https://github.com/liuandy1207/notes/assets/72530429/f0cb7b0a-0363-4d7c-96d2-88d88de9df90">

In the figure above, `char` only needs 1 byte, but 4 are reserved to enforce alignment. <br>

<img width="360" alt="Screenshot 2024-02-06 at 11 54 06 AM" src="https://github.com/liuandy1207/notes/assets/72530429/196946ad-46d1-45ae-a6c2-b0cb41f59032">

In the figure above, two of the fields are `char` for each `struct`. `s1` has the `char`s seperated and `s2` has them together. <br>
The `char`s that are apart will require 4 bytes of space each to enforce alignment, but the `char`s that are together will be packed together into one slot of 4 bytes. 













