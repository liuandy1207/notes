## Division Operator - `/`
Integer division **truncates** (rounds towards zero).
```C
9 / 10 = 0
(-9) / 10 = 0

```

## Size Operator - `sizeof()`
Returns the number of bytes required to store the input value.
```C
sizeof(TYPE);
sizeof(IDENTIFIER);

```

## Field Access Operator - `.`
```C
STRUCT_IDENTIFIER.FIELD    // access FIELD of STRUCT_IDENTIFIER

// EXAMPLE
struct posn {
  int x;
  int y;
};

struct posn p = {1, 2}; // see note

p.x      // access field x
p.y = 1  // change field y to 1

```

## Address Operator - `&`
Returns the adress of an identifier in memory in hex. 
```C
int val = 1;

printf("Address of val: %p", &val);

```

## Indirection (Dereference) Operator - `*`
The indeirection operator is the "inverse" of the address operator. <br>
Returns the value of a pointer's address.
```C
int val = 1;
int *pval = &val;

printf("Value of val: %d", *pval);

```

## Indirection Selection Operator - `->`
Returns a field from a pointer that points to a `struct`.
```C
pSTRUCT_IDENTIFIER->FIELD

// EXAMPLE
struct posn {
  int x;
  int y;
};

struct posn my_posn = {1, 2};
struct posn *pposn = &my_posn;

pposn->x    // access field x from my_posn
(*pposn).x  // an equivalent expression, brackets necessary because of precedence

```












