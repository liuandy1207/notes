## Data Type - Pointers `*`
Pointers are defined by placing a `*` after the type. <br>
The `*` is part of syntax, NOT the identifier. <br>

The value of a pointer is an address. 

```C
TYPE IDENTIFIER = TYPE_VALUE;
TYPE *pIDENTIFIER = &TYPE_VALUE;

// EXAMPLE
int val = 136;
int *pval = &val;   // the pointer pval "points at" val

```
