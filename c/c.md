---
title: C programming language
description: My C knowledge
---

<br> [<kbd> <br> HOME <br> </kbd>][HOME] <br>

# Table of contents
- [Table of contents](#table-of-contents)
- [1. C keywords](#1-c-keywords)
- [2. Variables declaration](#2-variables-declaration)
- [3. Memory Layout](#3-memory-layout)
- [4. Volatile keyword](#4-volatile-keyword)
- [5. Pointer](#5-pointer)
- [6. Function pointer](#6-function-pointer)
- [7. Struct & Union & Enum](#7-struct--union--enum)
- [8. Extern & Static](#8-extern--static)
- [9. Compilation Model](#9-compilation-model)
- [10. Static & Dynamic Library](#10-static--dynamic-library)
- [11. Function Invoker](#11-function-invoker)
- [12. Inline Function](#12-inline-function)
- [13. Dynamic Memory Allocation](#13-dynamic-memory-allocation)

## 1. C keywords

 auto           | double	    | int	          | struct 
 :---:          | :---:         |  :---:          | :---:        
 **break**	    | **else**	    | **long**	      | **switch**    
 **case**	    | **enum**	    | **register**	  | **typedef**   
 **char**	    | **extern**	| **return**	  | **union**     
 **continue**	| **for**	    | **signed**	  | **void**      
 **do**	        | **if**	    | **static**	  | **while**     
 **default**	| **goto**	    | **sizeof**	  | **volatile**  
 **const**	    | **float**	    | **short**	      | **unsigned**  

## 2. Variables declaration
*type-qualifier(s) type-modifier data-type variable-name = initial-value;* \
`type-qualifier`: *const, volatile, restrict* \
`type-modifier`: *short, long, unsigned, signed* \
`data-type`: *integer (int), floating point (double, float), enumerated, derived (array, struct, union, pointer), void* 

## 3. Memory Layout
**Memory layout** from low to high addresses in C includes: 
* **code(text) segment**: executable instructions - sharable & read-only
* **initialized data**: global variables, static variables initialized (declared $\neq$ 0)
* **uninitialized data**: global variables, static variables uninitialized or initialized to 0
* **heap**: dynamic memory allocation (forget deallocation cause **Memory leak**)
* **stack**: automatic variable storage, function frame (runout of *stack memory* cause **Stack overflow**)

**Notice**: memory layout in C is not memory layout in computer, this will be discussed in Operating Systems part

## 4. Volatile keyword
**volatile**: used to indicate to the compiler that a variable's value may change unexpectedly \
*volatile* is usually used when you turn on compiler's optimization function 
* Peripheral register mapping to memory 
* Interrupt Service Routines (ISRs) 
* Multi-thread applications
**const volatile**: same as volatile but you can't change its value by the code

## 5. Pointer:
**pointer** is variables that hold address \
*pointer* point to any type have same size \
In C, we don't have reference parameter so we can use *pointer* to substitute

## 6. Function pointer:
**function pointer** is a pointer to const because function address place on *code segment* which is *read-only* \
*syntax*: data-type (*function-name)(parameter) \
e.g. `void (*pointer_function)()`: pointer function point to a function with no parameter and return void

## 7. Struct & Union & Enum
**struct**, **union** and **enum** are user-define data types \
**struct** is used to group related variables (members) into one  
`struct in C` need to use *typedef* to don't use *struct* keyword whenever declare a new *struct variable*. In C++, it is not necessary \
**union** allows to store different data types to same memory     \
**enum** is usually used to assign name to integral constants \
`data structure alignment` is the term that means compiler "padding" into space between 2 data "naturally aligned", this mechanism help compiler better performance. We should arrange data in *struct* reasonable to optimize memory and performance

## 8. Extern & Static
**extern** is used to notify to the compiler that variable is memory allocated and don't need to allocate again, it is usually used in multi-source file projects \
**static** have 2 meaning: 
* If a variable is declared as global, that variable is only used in that file (multi-source file projects)
* Else if that variable is declared as local in a function (or a class in C++), that variable is memory allocated once until the program ends meaning that the variable will not be destroyed when the function call ends so it will use its last "state" when the function called again

## 9. Compilation Model
**Preprocessing**: *preprocessor* will replace preprocessor directives (#) \
**Compiling**: *compiler* will compile code to assembly code (.s/.asm) \
**Assembling**: *assembler* will change assembly code to machine code in object code files(.o) \
**Linking**: *linker* will link object code files together to *shared library* or *executable file* \
A little bit about *preprocessing* and *linking*: *preprocessing* replaces header file (.h) but it usually only contains declarations not definitions and the *linking* link the definitions to these declarations

## 10. Static & Shared Library
**Static library** is linked in compile time \
**Shared/Dynamic library** is linked in run time

## 11. Function Invoker
When you invoke a function, there are 2 important additional parts called **prologue** and **epilogue** \
`prologue` is the concealed code run before the function is invoked, it is responsible to take the function's parameter to save to *stack* \
`epilogue` is the concealed code run after the function is invoked, it is responsible for returning the function's result to the function invoker and removing the parameter saved to *stack* \
*function*, *prologue* and *epilogue* take the same memory size no matter how many times the function is invoked which means the more you call the function, the more memory is saved \
But there is a paradox in programming that the advantage in memory comes with the disadvantage in speed \
The worst case is the function is too short that is shorter than *prologue*/*epilogue*

## 12. Inline Function
**inline** is used to define a macro-like function, meaning that the function's instructions will be replaced directly to its invoke in *preprocessor* step \
This helps improve speed but paying by program size

## 13. Dynamic Memory Allocation
As discuss in [**1.3. Memory Layout**](#13-memory-layout) there is a memory layer for *dynamic memory allocation* called heap. So how we manage *dynamic memory allocation* \
There are some keyworks to manage dynamic memory
* **malloc**: dynamically allocates a single large block of memory, returns *void* pointer and has the default garbage value initially. \
**Syntax**: `ptr = (data-type*)malloc(byte-size)`
* **calloc** like *malloc* but has some differences: dynamically allocates the number of blocks of memory, blocks initialized with default value 0. \
**Syntax**: `ptr = (data-type*)calloc(size, element-size)`
* **realloc**: dynamically change the memory allocation of a previously allocated memory, maintains the already present value and new blocks will be initialized with the default garbage value. \
**Syntax**: `ptr = realloc(ptr, new byte-size)`
* **free**: dynamically de-allocate the memory. \
**Syntax**: `free(ptr)`

<br> [<kbd> <br> FEEDBACK <br> </kbd>][FEEDBACK]<br>

[HOME]: ../README.md
[FEEDBACK]: https://github.com/friendlydenji/notebook/discussions