# C Abstract Data Types (ADTs)

## Data Structures vs. ADTs
With data structures, the client KNOWS THE STRUCTURE of the data and can DIRECTLY ACCESS the data. <br>

With ADTs, the client does NOT know the structure of the data and can only access data through the INTERFACE provided by the ADT. <br>

## Stack ADT
Stacks exhibit LIFO behaviour (last in, first out).

### Typical Stack Operations
- **PUSH**
&emsp; → adds an item to the top of the stack
- **TOP**
&emsp; → returns the item at the top of the stack
- **POP**
&emsp; → removes the item at the top of the stack and returns it
- **EMPTY?**
&emsp; → determines if the stack is empty or not

## Queue ADT
Queues exhibit FIFO behaviour (first in, first out).

### Typical Queue Operations
- **ENQUEUE**
&emsp; → adds an item to the end of the queue
- **FRONT**
&emsp; → returns the item at the front of the queue
- **DEQUEUE**
&emsp; → removes the item at the front of the queue and returns it
- **EMPTY?**
&emsp; → determines if the queue is empty or not

## Sequence ADT
Sequences can insert and retrieve/delete items at any arbitrary position within them.

### Typical Sequence Operations
- **LENGTH**
&emsp; → return the number of items in the sequence
- **INSERT**
&emsp; → insert a new item at a given position
- **AT**
&emsp; → returns the item at a given position
- **REMOVE**
&emsp; → removes the item at a given position and returns it

## Oversized Arrays
To circumvent the need to know the length of an array in advance, we can create OVERSIZED ARRAYS that have space for more elements than likely neccessary. <br>

Oversized arrays keep track of the MAXIMUM POSSIBLE length and a CURRENT length (the number of elements currently stored). <br>
Note that maximums are wasteful if excessively large, but restrictive if too small. 

### Exceeding the Max Length
When the max length of an oversized array is exceeded, possibilities include:

- Assertions failing
- Error messages (with or without modification)
- Special return value








