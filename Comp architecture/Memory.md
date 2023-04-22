Consists of:

- **Accumulator** #Accumulator
Stores the results of calculations made by the ALU.

- **Program counter** #PC
Keeps track of the memory locations of the next instructions to be dealt with. It then passes this next address to the #MAR.

- **Memory address register**  #MAR
Stores the memory locations of instructions that need nto be fetched from memory or stored into memory.

- **Memory Data Register**  #MDR
(or memory buffer register)
Stores the data being transferred to and from the storage. It contains a copy of the value in the memory location specified by the [memory address register](https://en.wikipedia.org/wiki/Memory_address_register).

- **Current Instruction Register**  #CIR
It stores the most recently fetched instructions while it is waiting to be coded and executed.

- **Instruction Buffer Register** #IBR
The instruction that is not to be executed immediately is placed in the instruction buffer register IBR.