# C Operators

## Arithmetic Operators
C uses **IN-FIX** notation. Normal arithmetic rules apply. <br>
Brackets may be used to specify order of operations. 

### Division Operator - `/`
Returns the quotient of two numbers. <br>
&emsp; → `int` division will **TRUNCATE** (round towards zero). In other words, decimals will be cut off. 

### Modulo Operator - `%`
Returns the remainder after integer division. 
```C
(a % b) = (a - (a / b) * b)

```
## Boolean Operators
```C
||  // or
&&  // and
!   // not

==  // equality
!=  // inequality

// Comparators
<
<=
>
>=

```
## Ternary Conditional Operator - `?`
```C
q ? a : b

```
Returns `a` if `q` is true, and `b` otherwise. 

## Intialization & Assignment Operator - `=`
```C
int n = 1;  // initialization
n = 2;  // assignment

```
Initializes a variable with a value or assigns a value to an existing variable.

### Additional Assignment Operators
```C
+=
-=
*=
/=
%=

++x  // increments x, then produces x
x++  // produces x, then increments x
--x
x--

```
&emsp; → `++x` is typically preferred over `x++`

## Size Operator - `sizeof(TYPE_OR_IDENTIFIER)`
Returns the number of bytes required to store the given data type or identifier. 

## Field Access Operator - `.`
Returns the value of the requested field for a structure.
```C
// SAMPLE VALUES
struct posn p = {3, 4};

p.x = 3
p.y = 4

```

## Address Operator - `&IDENTIFIER`
Returns the location of an identifer in memory. 

## Indirection (Dereference) Operator - `*`
Returns the value of an address in memory. <br>
It is the inverse of the address operator. 

### Levels of Indirection 
It is possible to have multiple levels of indirection. <br>
That is, pointers can point to pointers, which can be derferenced many times back to back. <br>
However, it is uncommon to have more than three levels of indirection.

## Indirection Selection Operator - `->`
Returns the value of the requested field for a structure pointer. 
```C
// SAMPLE VALUES
struct posn p = {3, 4};
struct posn *pp = &p;

pp->x = 3    // same as (*pp).x    note: the brackets () are REQUIRED!

```

## Array-Index Operator - `[INDEX]`
Returns the value at `INDEX` in a specific array.















