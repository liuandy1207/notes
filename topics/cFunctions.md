## Text Output - `printf`
Prints to standard output. 
```C
printf("STRING");

// EXAMPLE
printf("Hello world!");
printf("This is a number: %d", 1);

// Format Specifiers (multiple can be used)
%d      // int
%c      // char
%f      // float
%p      // hex (addresses)

// Special Characters
\n      // newline character
%%      // % sign
\\      // \ symbol
\"      // " mark
\'      // ' mark

```

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

## Input - `scanf`
Reads input froms standard input. <br>
Requires a pointer to a variable to store the value read in from stdin. 
```C
scanf("%d", &input);   // reads in one integer, stores it in the variable input
scanf("&c", &input);   // reads in one character, including whitespace
scanf(" &c", &input);   // reads in one character, ignoring whitespace

```
Multiple format specifiers can be used to read in more than one value. <br>

`scanf` either returns the quantity of values successfully read OR the constant `EOF` to indicate that the End Of File has been reached. Always check this value. 










