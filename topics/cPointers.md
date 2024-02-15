## Data Type - Pointers `*`
Pointers are defined by placing a `*` after the type. <br>
The `*` is part of syntax, NOT the identifier. <br>

The value of a pointer is an **address**. <br>
In `k`-bit systems, memory addresses are `k` bits long, so pointers require `k` bits to store an address. <br>
The size of a pointer is always the **same size**, regardless of the data type stored at the address. 

```C
TYPE IDENTIFIER = TYPE_VALUE;
TYPE *pIDENTIFIER = &TYPE_VALUE;

// EXAMPLE
int val = 136;
int *pval = &val;   // the pointer pval "points at" val

```

<img width="510" alt="Screenshot 2024-02-15 at 4 00 38 PM" src="https://github.com/liuandy1207/notes/assets/72530429/c714a243-76c4-4486-bb13-c09f809c250c">

## Dereferencing
The address operator `&` obtains the address of an identifier. <br>
The indirection operator `*` obtains the value located at an address. <br>

It is possible to have multiple levels of indirection when pointers point to other pointers before pointing at an identifier. <br>
C does not limit the number of levels of indirection. However, more than three levels is uncommon. 
```C
int val = 136;
int *pval = &val;    // pval points at val
int **ppval = &pval; // ppval points at pval
```
`pval` is an `int`-pointer. `ppval` is an `int`-pointer-pointer. <br>
