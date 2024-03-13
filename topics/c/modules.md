# C Modules
Modularization is the act of dividing large programs into well-defined modules. <br>

CLIENTS are other files that require functions that a module provides. <br>
Modules can be clients, but different modules should not cyclically depend on each other. <br>
The ROOT client contains the `main` function. <br> 

Modules are also called LIBRARIES. <br>

Modules are broken up into TWO FILES:
1. HEADER-FILE <br>
&emsp; → contains documentation and declarations <br>
&emsp; → provides the INTERFACE of the module <br>
&emsp; → .h extension <br>
2. SOURCE-FILE <br>
&emsp; → contains definitions <br>
&emsp; → provides the IMPLEMENTATION of the module <br>
&emsp; → .c extension <br>

## Advantages of Modularization
1. **REUSABILITY** <br>
&emsp; → good modules can be used by many clients <br>
&emsp; → it is possible to buy or license third-party modules <br>
&emsp; → it is also possible to subcontract parts of implementation
2. **MAINTAINABILITY** <br>
&emsp; → single modules are easier to test, compared to a large program <br>
&emsp; → if bugs are discovered, only the module containing the bug needs to be fixed
4. **ABSTRACTION** <br>
&emsp; → clients only need to know HOW TO USE a module, not how it works <br>
&emsp; → modules can easily be replaced with improved versions without losing compatibility

## Information Hiding
Interface is designed to hide implementation details from the client. <br> 

### Advantages of Information Hiding
1. **SECURITY** <br>
&emsp; → prevents clients from directly accessing data stored within a module <br>
&emsp; → clients may only interact with the module through the given interface <br>
2. **FLEXIBILITY** <br>
&emsp; → the underlying implementation of a module without affecitng the client (as long as interface remains unchanged)

## Declaration vs. Definition
DECLARATIONS introduce an identifier. <br>
DEFINITIONS gives some content to an identifier. <br>

Definitions are always declarations. <br>
Identifiers can be declared multiple times, but only DEFINED ONCE. <br>
Identifiers must be DECLARED before their use. 

### Functions: Declaration vs. Definition
```C
// DECLARATION
extern TYPE IDENTIFIER(PARAM_1_TYPE PARAM_1, ...)

// DEFINITION
TYPE IDENTIFIER(PARAM_1_TYPE PARAM_1) {
  // FUNCTION BODY
}

```
&emsp; → `extern` is optional for function declarations

### Global Data: Declaration vs. Definition
```C
// DECLARATION
extern const TYPE IDENTIFIER;
extern TYPE IDENTIFIER;

// DEFINITION
const TYPE IDENTIFER = TYPE_VALUE;
TYPE IDENTIFER = TYPE_VALUE;

```

### Structures: Declaration vs. Definition
```C
// INCOMPLETE DECLARATION
struct IDENTIFIER;

// COMPLETE DECLARATION
struct IDENTIFIER {
  FIELD_1_TYPE FIELD_1;
  ...
};

// DEFINITION
struct IDENTIFER = {FIELD_1};

```
&emsp; → structure that were declared incompletely are OPAQUE STRUCTURES <br>
&emsp; &emsp; → the client can only define POINTERS to opaque structures since the compiler does not know how much memory to allocate for the opaque strcture <br>
&emsp; &emsp; → TRANSPARENT STRUCTURES are structures that were declared completely in the interface file <br>
&emsp; → opaque structures do not share information about or access to a structure's fields with the client, allowing for a increased level of information hiding <br>



## Standard Modules
```C
<assert.h>   // provides assert
<limits.h>   // provides INT_MAX and INT_MIN
<stdlib.h>   // provides NULL, EXIT_SUCCESS, EXIT_FAILURE, exit, abs, malloc, realloc, and free
<stdio.h>    // provides printf, scanf, and EOF

```
&emsp; → use `<>` for standard modules <br>
&emsp; → use `""` for non-standard modules


