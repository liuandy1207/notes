## Arrays
Data structures that contain a FIXED NUMBER of elements of the SAME TYPE. <br>
Each element (individual value) is stored at an index of consecutive integers, starting at 0.
```C
int LABEL[LENGTH] = {value1, value2, ...}; // initializing an array

int LABEL[INDEX] = new_value; // mutating the value at INDEX

```
To define an array, the length must be known IN ADVANCE.<br>
Braces {} can only be used during initialization, but not assignment. <br>
Once defined, an entire array cannot be mutated at once. Only individual elements can be mutated. 

### Uninitalized Global vs. Local Arrays
Uninitialized global arrays are zero-filled. <br>
Uninitialized local arrays are filled with arbitrary values from the stack (???).

### Character Arrays
```C
char LABEL[LENGTH] = "ABCDE";        // intialized character array, NOT a string

char LABEL[LENGTH] = {'A', 'B', 'C', 'D' 'E'};     // equivalent expression

```


