# C Style Guide

## Function Documentation
```C
// IDENTIFER(PARAM, PARAM) verb (description of what the function does)
// requires: any restrictions on parameters
// effects: any side effects

```

### Requirement Assertions
Always assert requirements. <br>
It is better style to have **multiple small assertions** rather than one big compound assertion.

### Common Side Effects
Write "**may**" in front of a side effect if it is not guarenteed to occur. <br>
Avoid having more than one side effect per expression. 
- reads from the console
- prints to the console
- mutates *POINTER

## General

### Comments
```C
// comment

/*
block comment 
*/

```

### Identifiers
- Identifers must start with a letter.
- Identifers can only contain alphanumeric characters and underscore.
- `underscore_style` (snake case) is preferred.

### Variables
- Always initailize variables. 
- Define variables in the smallest scope possible and as close to its first use as possible.

### Blocks
- `{` appears at the end of a line.
- `}` appers at the start of a line and is aligned with the line that started it.
- Body statements are indented by **2 spaces**.

### Operators
- Spaces are required around arithmetic operators and after commas.
