# C Pointers
The data type of an **ADDRESS** is a **POINTER**. <br>
In a $k$-bit system, memory addresses are $k$ bits long, so pointers require $k$ bits to store an address. 
```C
// SAMPLE VALUES
int val = 136;
int *pval = &val;    // * is part of syntax, NOT the identifier

```

## `NULL` Pointers
`NULL` is a special pointer value to represent that the pointer points to **NOTHING**. <br>
It is good style to assign `NULL` to pointers when:
1. The value of the pointer is unknown at definition.
2. The value at the pointer's address becomes invalid.

Dereferencing a `NULL` pointer will crash the program. 

`NULL` is considered false in a boolean context. <br>

## `void` Pointers 
`void` pointers can point at anything. 

## Pointer Assignment
<img width="852" alt="Screenshot 2024-03-02 at 9 24 24 PM" src="https://github.com/liuandy1207/notes/assets/72530429/ff3719de-fb88-4ca5-9dcd-5dfb6b126734">
<img width="863" alt="Screenshot 2024-03-02 at 9 25 43 PM" src="https://github.com/liuandy1207/notes/assets/72530429/82fbeff4-537d-4be3-95c9-b5e2eec709ee">
<img width="853" alt="Screenshot 2024-03-02 at 9 24 45 PM" src="https://github.com/liuandy1207/notes/assets/72530429/599d723c-7cd0-47a1-8a2d-68e0258922d2">

&emsp; → `pi` is mutated to point at whatever `pj` is pointing at. 
<img width="871" alt="Screenshot 2024-03-02 at 9 26 55 PM" src="https://github.com/liuandy1207/notes/assets/72530429/0b20c3be-f07b-4d83-9644-a1951520d92c">

&emsp; → `*pi` is mutated to become `*pj`. That is, `i` becomes `j`.

## Aliasing
Aliasing is when multiple pointers point to the same address in memory. 

## Pass by Reference
Pass by reference occurs when pointers are passed to functions. <br>
This allows a function to directly write into the stack frame of the caller function (side effect). <br>
Then, this allows a function to "return" more than one value to the caller function. <br>

Many functions only return integers corresponding to exit codes. They achieve their main purposes through pass by reference. <br>
Functions must **NEVER** return addresses within its own stack frame. 

To avoid structure copying, always pass the **ADDRESS** of a structure instead of a copy. 

### Preventing Side Effects (`const` Pointers)
For a non-pointer value, `const` enforces that the parameter is immutable **WITHIN** the function. <br>
It does **NOT** require the passed parameter to be constant. 

```C
// SAMPLE VALUES
int i = 0;

int *ptr = &i;                 // ptr can point to any mutable int

const int *ptr = &i;           // ptr can point to any int, but the value of the int cannot be modified through dereferencing

int * const ptr = &i;          // ptr always points at mutable int i, it cannot be reassigned to another address

const int * const ptr = &i;    // ptr always point at int i

const int * const * const ptr = &ptr;   // prevents the mutation of the underlying value at any level of indirection 

```












