
**Instruction pipelining** is a [technique](https://simple.wikipedia.org/wiki/Technique "Technique") used in the design of modern [microprocessors](https://simple.wikipedia.org/wiki/Microprocessor "Microprocessor"), [microcontrollers](https://simple.wikipedia.org/wiki/Microcontroller "Microcontroller") and [CPUs](https://simple.wikipedia.org/wiki/Central_processing_unit "Central processing unit") to increase their [instruction](https://simple.wikipedia.org/wiki/Instruction_(computer_science) "Instruction (computer science)") throughput (the number of instructions that can be executed in a unit of time). Only works with RISC machines
![[Pasted image 20221203111118.png]]
(Upper with with command pipelining, lower without command 
pipelining)
![[Pasted image 20221203113004.png]]
This way the elements of the computer dont stay idle for as long as without pipelining.

### Hazards

#### Resource hazards
Happens when two instructions want to access the same resource at the same time.

**example:**
Consider the main memory you have has a single port that restricts the processor to perform instruction fetch, read data and write data one at a time. This means you cannot perform the operand read & write operation, from memory in parallel with instruction fetch.
![[Pasted image 20221203113527.png]]
So we would halt the instruction fetch of instruction 3 for one clock cycle. Because instruction 1 will fetch its source operand from memory so in the same clock cycle instruction 3 cannot perform instruction fetch in parallel to operand fetch of instruction 1.

#### Data Hazards
The data hazard is a condition when accessing an operand location creates conflict. Consider that you have two instructions:
``` fortran
ADD R1, R2, R3

SUB A, R1
```

Observe the instructions above the result of add instruction is stored in register R1 after the execution. This R1 act as an operand for subtract instruction. Now in the figure below notice that the register R1 is updated with the add result in clock cycle t4. But the subtract instruction need its operand R1 at the t3 clock cycle. But if subtract instruction fetches the operand R1 in the t3 clock cycle then it will generate an incorrect result.
![[Pasted image 20221203113843.png]]
So the subtract instruction must stall or halt for two clock cycles because for the correct result the subtract instruction is dependent on the result of add instruction. This dependency is also called _data dependency_.

#### Control Hazards
Control hazards occur when instruction pipelining fails in predicting branches in the instruction. Let us understand this with the help of an example. Consider the first instruction I1 in the pipeline is a branch instruction that targets instruction I6.

The instruction I1 is fetched in cycle t0, decoded in cycle t1, fetch operands in cycle t2 and perform execution in cycle t3 where the target address is computed. But till then three instructions I2, I3 and I4 are pipelined in cycle t1, t2 and t3 which must be discarded as instruction I1 is branch instruction which will compel the processor to execute the instruction I9 after instruction I1.

This is how control hazards lead to delay of three cycles t1, t2 and t3 between I1 and I 6 which is also termed as _branch delay_. (En gros on a fait des instructions pour rien)
![[Pasted image 20221203114634.png]]
This branch delay could be minimized if the branches in the instruction could be predicted at the decoding stage only.
**Solution:** ==Insertion of empty operations (NOP)==
We go from:
```assembly
start: BEQ R1, R2, else: // if (R1 == R2)
ADD R1, #1; // R1 = R1 + 1;
JMP end: // else
else: ADD R2, #1; // R2 = R2 + 1;
end: ...
```
To:
```assembly
start: BEQ R1, R2, else:
NOP
NOP
NOP
ADD R1, #1;
JMP end:
NOP
NOP
NOP
else: ADD R2, #1;
end: ...
```
**Other solution:** ==Speculative execution of instructions ==
In [computer architecture](https://en.wikipedia.org/wiki/Computer_architecture "Computer architecture"), a **branch predictor** is a [digital circuit](https://en.wikipedia.org/wiki/Digital_electronics "Digital electronics") that tries to guess which way a [branch](https://en.wikipedia.org/wiki/Branch_(computer_science) "Branch (computer science)") (e.g., an [if–then–else structure](https://en.wikipedia.org/wiki/Conditional_(programming) "Conditional (programming)")) will go before this is known definitively. The purpose of the branch predictor is to improve the flow in the [instruction pipeline](https://en.wikipedia.org/wiki/Instruction_pipeline "Instruction pipeline"). Branch predictors play a critical role in achieving high [performance](https://en.wikipedia.org/wiki/Computer_performance "Computer performance") in many modern [pipelined](https://en.wikipedia.org/wiki/Instruction_pipelining "Instruction pipelining") [microprocessor](https://en.wikipedia.org/wiki/Microprocessor "Microprocessor") architectures such as [x86](https://en.wikipedia.org/wiki/X86 "X86").

![[Pasted image 20221203115348.png]]
**1-bit predictor**
The 1 bit records the previous branch decision (taken or not taken) and switches to the other if the prediction turned out to be false.
![[Pasted image 20221203120616.png]]

**The 2-bit branch history table predictor**
We have 4 states encoding how sure taking the conditional branc will be (based on previous desision we change to the corresponding state
![[Pasted image 20221203120906.png]]
![[Pasted image 20221203120921.png]]

## Superpiplining

## Superscalar architecture (ex $\alpha$ processor)
- Multiple parralel pipelines that can perform the same instruction?