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

## Variable Initialization
```C
TYPE IDENTIFIER = TYPE_VALUE;   // declaration + initialization

const TYPE IDENTIFIER = TYPE_VALUE; // for constants

```
If a variable is declared inside a function, it is **local**. Otherwise, it is **global**. 

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

## Iteration - `while`
```C
// While Loop
SETUP_STATEMENT; // looper variable definition
while (PREDICATE) {
  ...
  UPDATE_STATEMENT; // update looper variable
}

// Do ... While Loop
SETUP_STATEMENT;
do {
  ...
  UPDATE_STATEMENT;
} while (predicate);

// Additional Loop Features
break;       // terminates the current loop
continue;    // skips other statements in the current block


```
`do ... while` loops always run **at least once** because the predicate is checked **after** execution of the body.

## Iteration - `for`
```C
for (SETUP_STATEMENT; PREDICATE; UPDATE_STATEMENT) {
  ...
}

// Special Ommitence Cases
for (; i < num; ++i) {..}     // i was previously defined
for (; i < num;) {...}        // same as while (i < num)
for (;;) {...}                // infinite loop

// EXAMPLE: multi-variable setup, predicate, and update
for (int i = 1, j = 100; i < j; ++i, --j) {...}

```
Commas can be used to have more variables in each portion of the `for` loop. 





























