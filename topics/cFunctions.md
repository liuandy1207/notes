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
The size of `int` varies between machines and OSs, but most systems use a 32-bit `int`.

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
