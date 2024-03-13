# C Modules
Modularization is the act of dividing large programs into well-defined modules. <br>

CLIENTS are other files that require functions that a module provides. <br>
Modules can be clients, but different modules should not cyclically depend on each other. <br>
The ROOT client contains the `main` function. <br> 

Modules are also called LIBRARIES.

## Advantages of Modularization
1. REUSABILITY <br>
&emsp; → good modules can be used by many clients <br>
&emsp; → it is possible to buy or license third-party modules <br>
&emsp; → it is also possible to subcontract parts of implementation
2. MAINTAINABILITY <br>
&emsp; → single modules are easier to test, compared to a large program <br>
&emsp; → if bugs are discovered, only the module containing the bug needs to be fixed
4. ABSTRACTION <br>
&emsp; → clients only need to know HOW TO USE a module, not how it works <br>
&emsp; → modules can easily be replaced with improved versions without losing compatibility

## Declaration vs. Definition
DECLARATIONS introduce an identifier. <br>
DEFINITIONS gives some content to an identifier. <br>

Definitions are always declarations. <br>
Identifiers can be declared multiple times, but only DEFINED ONCE. 
