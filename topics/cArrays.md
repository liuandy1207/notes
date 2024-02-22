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

## Uninitalized Global vs. Local Arrays
Uninitialized global arrays are zero-filled. <br>
Uninitialized local arrays are filled with arbitrary values from the stack (???).

## Character Arrays
```C
char LABEL[LENGTH] = "ABCDE";        // intialized character array, NOT a string

char LABEL[LENGTH] = {'A', 'B', 'C', 'D' 'E'};     // equivalent expression

```

## Array Length
C does NOT explictly track array length. Keep track of it seperately.
```C
EXAMPLE: 
int my_array[3] = {1, 2, 3};
const int my_array_length = 3;

```

## Array Size
Array size is the NUMBER OF BYTES it occupies in memory. <br>
An array of $k$ elements, each of size $s$, requires $k \times s$ bytes. <br>
In the C memory model, each element of an array is placed in memory immediately after the previous element. 

## Dereferencing Arrays
Dereferencing arrays is equivalent to accessing the first element of the array. 

## Arrays as Function Parameters
When an array is passed to a function, only the ADDRESS OF THE FIRST ELEMENT is copied into the stack frame. <br> 
Furthermore, you should assert these parameters to not be `NULL`. <br>

If a function should not mutate the contents of an array, declare parameters with `const`. <br>
```C
// EXAMPLE: array summer
int sum_array(int data[], const int data_len) {
  int sum = 0;
  for (int i = 0; i < data_len; ++i) {
    sum += data[i];
  }
  return sum;
}

```











