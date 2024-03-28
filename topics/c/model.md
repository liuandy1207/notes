# C Model of Computation

## Control Flow
At execution, the program location starts at the entry point (beginning of `main` function). <br>
As execution proceeds, the program location continues to be tracked. <br>

When a function is called, the program location jumps to the start of that function. <br>
When the keyword `return` is reached, the program locations returns back to the calling function. <br>

## Structure of Memory
One bit can either be `0` or `1`. <br>
One byte consists of `8` bits.

The smallest **ADDRESSABLE** (accessible) unit of memory is a byte. <br>
To access a block of memory, you must know its address (position) in memory. <br> 
Memory addresses are typically represented in hexadecimal.

Computer memory can be visualized as a collection of labeled mailboxes. <br>
Each mailbox stores a byte. 
<img width="1121" alt="Screenshot 2024-03-02 at 3 45 11 PM" src="https://github.com/liuandy1207/notes/assets/72530429/43d78a24-a1a5-4495-8e8c-d590b0b4557d">

### Defining Variables 
Whenever a variable is defined in C,
1. Sufficient space is reserved in memory to store the variable.
2. The address of the space is associated with the identifier of the variable.
3. The initial value of the variable is written to that address. 
<img width="928" alt="Screenshot 2024-03-02 at 3 48 24 PM" src="https://github.com/liuandy1207/notes/assets/72530429/bcafdd51-2450-41b3-9b7d-24bbcfd466ca">

### Integer Overflow
C uses 4 bytes to store an `int`, so there are only $2^{32}$ values that can be represented. <br>
The range of C `int` values is $\[-2^{31}, 2^{31} - 1\]$. <br>
Any value outside of this range will result in **INTEGER OVERFLOW** and the value will be **UNDEFINED**.

## Sections of Memory
<img width="855" alt="Screenshot 2024-03-02 at 8 22 47 PM" src="https://github.com/liuandy1207/notes/assets/72530429/074c20a2-094b-4b7e-a866-9d894e619044">

### Code Section
Human-readable code is compiled into machine code just before execution. <br>
Machine code is moved to this section of memory for execution. 

### Global Constants and Global Variables Sections
Global constants and global variables are available throughout the execution of a program. <br>
These spaces is reserved before the program begins execution. <br>
Space for global constants is reserved before space for global variables.<br>
Both global memory sections are created and intialized at **COMPILE TIME**. 

### Stack Frames
Every function call generates a stack frame. Space for the stack frame is only reserved upon a function call. <br>
When a function returns, the stack frame is removed and the control flow returns the caller. 

Stack frames begin at the **HIGHEST** memory address available. <br>
Each subsequent stack frame is placed at increasingly lower addresses. <br>
**STACK OVERFLOW** occurs when the stack grows large enough to collide with other sections of memory. 

Each stack frame contains:
- The values of each parameter
- All local data (variables and constants) within the function block.
  - The intial values of local data are set when their definition is encountered. 
- The return address (location inside the calling function).


**Pass by Value** <br>
When a stack frame is created, a **COPY** of each parameter and the return address is placed in the stack frame. <br>

**Uninitialized Memory** <br>
For global data, C automatically initializes the variable to `0`. <br>
However, it is good style to intialize global variables explicitly. 

For local data, C writes an arbitrary (garbage) initial value from the stack.  

### The Heap
The heap can be thought of as a big "pool" of memory that is available to your program. <br>

Memory here is ALLOCATED from the heap upon request. <br>
This memory is borrowed and must be returned (freed) back to theheap when it is no longer needed (memory deallocation). <br>
Returned memory can be reused for a future allocation. <br>

If too much memory has already been allocated, attempts to borrow additional memory will fail. 

**Advantages of the Heap** <br>
- DYNAMIC: the size of memory to be allocated can be determined at runtime
- RESIZABLE: allocated memory can be resized
- SCOPE: allocated memory persists until it has been freed, functions can allocate memory that continues to be valid after the function returns
- SAFETY: if memory runs out, it can be detected and handled properly (unlike stack overflows)
- USER-MANAGED: unlike stack memory that is managed by the system, users must explicitly manage heap memory themselves






