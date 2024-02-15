## General Function Template
```C
// General Function
TYPE IDENTIFIER(PARAMETERS) {
  ...
  return TYPE_VALUE;
}

// General Function, No Parameters
TYPE IDENTIFIER(void) {
  ...
  return TYPE_VALUE;
}

// Void Function
void IDENTIFIER(PARAMETERS) {
  ...
  return; // optional
}

```

## Boolean Operators
```C
||     // or
&&     // and
!      // not

==     // equality
!      // inequality
<
<=
>
>=

```

## Conditional Statements
```C
if (PREDICATE) {
  ...
} else if (PREDICATE) {
  ...
} else {
  ...
}

```
If the function is non-`void`, every conditional path needs to end with a `return` statement.

## Text I/O with `printf`
```C
printf("Hello world!");
printf("This is a number: %d", 1);

// Input Placeholders
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















