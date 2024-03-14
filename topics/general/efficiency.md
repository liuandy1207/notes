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
