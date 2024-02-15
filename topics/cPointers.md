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

## `NULL`
`NULL` is a special pointer value to represent that the pointer points to nothing. <br>
If the value of a pointer is unknown at the time of definition, it is good style to assign `NULL` to the pointer. <br>
Also, `NULL` is considered to be **false** in a Boolean context. <br>

Dereferencing `NULL` pointers will cause the program to crash.

## `void`-Pointers
`void`-pointers can point at anything.
```C
void *p = NULL;

```

## Pointer Assignment
<img width="694" alt="Screenshot 2024-02-15 at 4 27 24 PM" src="https://github.com/liuandy1207/notes/assets/72530429/f6bc70ea-c435-4c27-904c-8e65ae48ec59">
In the figure above, a pointer assignment is performed. `pi` is mutated to point to what `pj` is pointing at. 

## Dereferencing and Assignment
<img width="689" alt="Screenshot 2024-02-15 at 4 27 52 PM" src="https://github.com/liuandy1207/notes/assets/72530429/9dccd979-4511-47ce-b62c-2d6e6d78f821">
In the figure above, a dereferentiatoin and an integer assignment is performed. The value `pi` points at is mutated to become the value `pj` points at. 

## Aliasing
Aliasing is when multiple pointers point to the same data in memory. 

## Pass By Value vs. Pass By Reference
In pass by value, a **copy** of each argument is passed. <br>
In pass by reference, a **reference** (pointer) to the stack frame of the caller function is passed. <br>

Pass by value returns the desired value to the caller. <br>

Pass by reference directly writes the desired value into the stack frame of the caller. This allows multiple data points to be returned to a caller function, instead of just one. <br>

ASIDE: Functions must **never** return an **address within its own stack frame**.



















