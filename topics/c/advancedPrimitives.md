# C Advanced Primitives

## Structures
The amount of memory reserved for a structure is **AT LEAST** the sum of the sizes in each field, but it may be **LARGER**. <br>
```C
// SAMPLE VALUES

// structure declaration
struct posn {
  int x;   // x and y are both FIELDS
  int y;
};    // note the closing semicolon

// definition and initialization
struct posn p = {3, 4};

```
&emsp; → The structure type includes the keyword `struct`. <br>
&emsp; → No memory is reserved for the structure declaration. Memory is only reserved on definition. 

### Structure Memory Padding
C may reserve additional space for a structure to improve efficiency and **ENFORCE ALIGNMENT** within the structure. <br>
Furthermore, size of a structure depends on the order of the fields. 
<img width="801" alt="Screenshot 2024-03-02 at 8 15 29 PM" src="https://github.com/liuandy1207/notes/assets/72530429/eb81307b-7216-494d-806f-2bd153dc8da4">
<img width="796" alt="Screenshot 2024-03-02 at 8 15 50 PM" src="https://github.com/liuandy1207/notes/assets/72530429/3a8a9dd7-5bc1-45d3-8c35-04579dde7b94">



