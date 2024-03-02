# C Basics

## Side Effects
Side effects occur when the **STATE** (value) of something changes. <br>
**PROCEDURAL PROGRAMMING** employs side effects, while functional programming does not. 

### I/O Side Effects
Changes the state of the system by reading input or producing output. 
### Mutation
Changes the state of the system by modifying memory and variables. <br>
Functions that mutate global variables or depend on global variables are **IMPURE**. 

## Program Entry Points 
Programs are typically executed by an Operating System through a shell or another program. <br>
To do so, the OS needs to know where to start running the program. This is the **ENTRY POINT**. <br>

In C, the entry point of a program is a special function called `main`. <br>
Every C program must have **EXACTLY ONE** `main` function. <br>
By calling `main`, the OS transfers **CONTROL FLOW** to the program. After execution, it is returned to the OS. 
```C
int main(void) {
  // ...
  return 0;   // exit code 0 indicates success
}

```

## Variables
```C
TYPE IDENTIFIER = INITIAL_VALUE;

```
Variables store **MUTABLE** state information (values). <br>
Variables must **ALWAYS** have a value. 

### Constants 
```C
const TYPE IDENTIFIER_IN_CAPS = VALUE; 

```
Constants store **IMMUTABLE** state information. <br>
Constants are recommended when applicable because they:
- Communicate the intended use of the variable,
- Prevent unintended mutation, and
- May help optimize code.

### Global vs. Local
Global data is defined **OUTSIDE** of functions. <br>
The scope of global data is anywhere **BELOW** its definition. <br>

Local data is defined **INSIDE** of functions. <br>
The scope of local data is **BETWEEN DEFINITION AND THE END OF THE BLOCK**. 

## Function Definitions
```C
RETURN_TYPE IDENTIFIER(TYPE PARAM1, TYPE PARAM2) {
  // ...
  return RETURN_VALUE;
}

```
&emsp; → The number of parameters is **NOT LIMITED**. <br>
&emsp; → The type of `RETURN_VALUE` must match `RETURN_TYPE`.

### `void` Functions
```C
void IDENTIFIER(TYPE PARAM) {
  // ...
  return;  // optional
}

```
&emsp; → No `return` statement required. Control flow is **IMPLICITLY** transferred back to the OS. 

### Parameterless Functions
```C
RETURN_TYPE IDENTIFIER(void) {
  // ...
  return RETURN_VALUE;
}

IDENTIFIER();  // do not pass void when calling the function

```

## Conditional Statements
```C
if (CONDITION) {
  // ...
} else if (CONDITION) {
  // ...
} else {
  // ...
}
```
&emsp; → Non-`void` functions requires every path to end with a `return` statement. 

## Iteration
```C
while (CONDITION) {
  // ...
}

do {
  // ...
} while (CONDITION);

break;  // immediately terminate the innermost loop
continue; // skips the rest of the statements in the current block


for (SETUP; CONDITION; UPDATE) {
  // ...
}

```
&emsp; → `do...while` statements are guarenteed to run **at least once** since the condition is checked after. <br>
&emsp; → Multiple definitions and expressions can be included in the setup and update of a `for` loop. Seperate with commas. <br>
&emsp; → Using `continue` in a `for` loop will execute the update statement before jumping back to the expression.

### Omitting Components of `for` Loops
```C
// SAMPLE VALUES
for (; i < 100; ++i) {...}    // i was previously defined
for (; i < 100;)              // equivalent to while (i < 100)
for (;;) {...}                // infinite loop

```

