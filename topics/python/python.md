# Python

## Lore 
- Developed by Guido van Rossum.
- Released in 1991.

## General
- Newlines signal new commands
- Indentation matters greatly (be consistent)

## Commenting
```python
# Single-line comment

""" Multi-line
    comment
"""

```

## Variables
Variable names are case-sensitive.

### Creation
All variables must be initialized to a value. They cannot just be declared. <br>
Variables are not declared to be any specific type, and can change type after assignment. 
```python
x = 1
x = "word"

# Multi-Variable Multi-Value Assignment
x, y, z = 1, 2, 3

# Multi-Variable Single Value Assignment
x = y = z = 1

```

### Casting
Variables can be cast to specify type.
```python
x = str(3)   # x will be '3'
y = int(3)   # y will be 3
z = float(3) # z will be 3.0

```

### Type Retrieval
Using `type(x)` will return the type of the value stored in the variable `x`.

## Strings
Strings can be declared with `''` or `""`.

### `print`
Prints the value in the variable `var`
```python
print(x)

print(x + y)   # if both non-numeric, concatenates and prints x and y
print(x + y) ` # if numeric, prints the sum of x and y

print(x, y)    # prints x and y, seperated by a space


```











