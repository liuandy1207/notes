# C Model of Computation

## Control Flow
At execution, the program location starts at the entry point (beginning of `main` function). <br>
As execution proceeds, the program location continues to be tracked. <br>

When a function is called, the program location jumps to the start of that function. <br>
When the keyword `return` is reached, the program locations returns back to the calling function. <br>

## Structure of Memory
One bit can either be `0` or `1`. <br>
One byte consists of `8` bits.

The smallest **ADRESSABLE** (accessible) unit of memory is a byte. <br>
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
