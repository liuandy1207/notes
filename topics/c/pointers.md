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
