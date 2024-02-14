## `clang` Compiler
The `clang` compiler can be used to compile C-based files into an executable.
```bash
clang FILE.c              # compiles the C file FILE.c
./a.out                   # executes the compiled file, notice the ./
./a.out < test.in         # providing input for execution of a.out

```
The default output file is titled `a.out`. <br>

If input is required `.in` files can be directed into the executable. `.args` and `.out` files can also be applied.

## Compiler Arguments
```bash
-std=C99       # comply with the C 1999 standard
-g             # generate source level debug info (line numbers)
-Wall          # warn all, do not supress any warnings
-o NAME        # rename the produced executable to the next given argument
-I/PATH        # provide a path to a directory that contains any necessary .h header files

Example:
clang main.c -I/u2/cs136l/pub/common/cs136.o -o myprogram

```
The order of compiler arguments does NOT matter (except for `-o`). <br>

Do not provide a direct path to any `.h` header files. Only provide their directory. <br>
Notice the syntax of `-I` in the example. PATH is connected to `-I`.
