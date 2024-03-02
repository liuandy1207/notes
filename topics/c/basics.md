# C Basics

## Side Effects
Side effects occur when the **state** (value) of something changes. <br>
**Procedural programming** employs side effects, while functional programming does not. 

### I/O Side Effects
Changes the state of the system by reading input or producing output. 
### Mutation
Changes the state of the system by modifying memory and variables. 

## Program Entry Points 
Programs are typically executed by an Operating System through a shell or another program. <br>
To do so, the OS needs to know where to start running the program. This is the **entry point**. <br>

In C, the entry point of a program is a special function called `main`. <br>
Every C program must have **exactly one** `main` function. <br>
By calling `main`, the OS transfers **control flow** to the program. After execution, it is returned to the OS. 
```C
int main(void) {
  // ...
  return 0;   // exit code 0 indicates success
}

```

## Function Definitions
```C
RETURN_TYPE IDENTIFIER(TYPE PARAM1, TYPE PARAM2) {
  // ...
  return RETURN_VALUE;
}

```
&emsp; → The number of parameters is **not limited**. <br>
&emsp; → The type of `RETURN_VALUE` must match `RETURN_TYPE`.

### `void` Functions
```C
void IDENTIFIER(TYPE PARAM) {
  // ...
  return;  // optional
}

```
&emsp; → No `return` statement required. Control flow is **impliclty** transferred back to the OS. 

### Parameterless Functions
```C
RETURN_TYPE IDENTIFIER(void) {
  \\ ...
  return RETURN_VALUE;
}

IDENTIFIER();  // do not pass void when calling the function

```

## Conditional Statements
```C
if (CONDITION) {
  \\ ...
} else if (CONDITION) {
  \\ ...
} else {
  \\ ...
}
```
&emsp; → Non-`void` functions requires every path to end with a `return` statement. 
