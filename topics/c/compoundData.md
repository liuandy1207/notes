# C Compound Data

## Structures
The amount of memory reserved for a structure is **AT LEAST** the sum of the sizes in each field, but it may be **LARGER**. <br>
No memory is reserved for the structure declaration. Memory is only reserved on definition. 
```C
// SAMPLE VALUES

// structure declaration
struct posn {
  int x;   // x and y are both FIELDS
  int y;
};    // note the closing semicolon

// definition and initialization
struct posn p = {3, 4};

// alternate methods of initialization
struct posn p = {.y = 4, .x = 3};
struct posn p = {.x = 3};    // omitted fields are filled with 0

```
&emsp; → The structure type includes the keyword `struct`. <br>
&emsp; → `{}` cannot be used for assignment, only for initialization. <br>
&emsp; &emsp; → Instead, fields must be accessed and mutated individually. <br>
&emsp; → Comparators and printf do not work with structures. To achieve their purposes, you must define your own functions. 

### Structure Memory Padding
C may reserve additional space for a structure to improve efficiency and **ENFORCE ALIGNMENT** within the structure. <br>
Furthermore, size of a structure depends on the order of the fields. 
<img width="801" alt="Screenshot 2024-03-02 at 8 15 29 PM" src="https://github.com/liuandy1207/notes/assets/72530429/eb81307b-7216-494d-806f-2bd153dc8da4">
<img width="796" alt="Screenshot 2024-03-02 at 8 15 50 PM" src="https://github.com/liuandy1207/notes/assets/72530429/3a8a9dd7-5bc1-45d3-8c35-04579dde7b94">

## Arrays
An array is a data structure that contains a **FIXED NUMBER** of elements of the **SAME TYPE**. <br>
Each element is stored at an **INDEX** of consecutive integers, starting at `0`.
```C
TYPE IDENTIFIER[LENGTH] = {...};

```
&emsp; → Definining arrays requires the length to be known beforehand. <br>
&emsp; → You may initialize with AT MOST `LENGTH` elements. If there are less than `LENGTH` elements, the remaining values are initialized to `0`. <br>
&emsp; → If `LENGTH` is not explicitly given, the compiler will impliclty calculate array length based on the number of elements provided during initialization. <br>
&emsp; → `{}` can only be used during initalization. It can not be used for assignment. 

### Uninitialized Arrays
Global arrays become zero-filled. <br>
Local arrays are filled with arbitrary (garbage) values from the stack.

### Character Arrays - `char[]`
Character arrays can be initialized with `""` for convenience. <br>
However, these are **NOT** strings.
```C
// SAMPLE VALUES
char pet[3] = "cat";
char pet[3] = {'c', 'a', 't'};     // equivalent expression

```















