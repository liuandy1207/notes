# Efficiency
Algorithms are step-by-step descriptions of how to solve a "problem". <br>
We use efficiency to objectively compare algorithms.

## Types of Efficiency
- **TIME EFFICIENCY** <br>
&emsp; → how long it takes an algorithm to solve a problem
- **SPACE EFFICIENCY** <br> 
&emsp; → how much space (memory) an algorithm requires to solve a problem
- **POWER EFFICIENCY** <br>
&emsp; → how much power is consumed by the algorithm to solve a problem

## Running Time - $T(n)$
Running time is measured by the number of ELEMENTARY OPERATIONS required to solve the problem. <br>

The length of the data is traditional represented by $n$. <br>
Often, $n$ is obvious by context, but if there is any ambiguity, you should clearly state what $n$ represents. 

Typically, algorithms are compared by their WORST CASE scenerios. 

### Constant Runtime
Regardless of the involved values, the number of EOs remains the SAME. 

### Linear Runtime
If the involved value is doubled, the number of EOs also (roughly) doubles. 

## Big $O$ Notation
Big $O$ notation represents the order of magnitude of a running time where order is the DOMINANT TERM in the runtime. 

All other terms (except the dominant term) are ignored because their impact is diminished with increasing amounts of data. 

### Big $O$ Arithmetic
When ADDING two orders, the result is the LARGEST of the two orders. <br>
When MULTIPLYING two orders, the result is the PRODUCT of the two orders. 

### Constant - $O(1)$
Non-repeated operation. 
Examples:
- operators
- calls to simple functions

### Logarithimic I - $O(\log n)$
$O(1)$ operation repeated less than $n$ times (fractioning data length). 

### Linear - $O(n)$
$O(1)$ operation repeated $n$ times. 
Example:
- simple array traversal

### Logarithmic II - $O(n \log n)$
$O(\log n)$ operation repeated $n$ times. 
Example:
- simple array traversal with $O(\log n)$ operation in loop body

### Quadratic - $O(n^2)$
$O(n)$ operation repeated $n$ times.
Examples:
- simple array traversal with $O(n)$ operation in loop body
- nested loops

### Cubic - $O(n^3)$

### Exponential - $O(2^n)$
One call results in multiple subsequent calls (complex recursion). 






