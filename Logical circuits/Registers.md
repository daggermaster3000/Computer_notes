**Shift Registers** are a form of computer memory. Usually implemented with chains of
- [[D Flip-Flop]] 
- [[SR Flip-Flop]] 
- [[JK Flip-Flop]] 
- [[Gated SR Flip-Flop]]
Where the output of one is connected to the next.

Similar to the earlier [delay-line memory](https://en.wikipedia.org/wiki/Delay-line_memory "Delay-line memory") systems and were widely used in the late 1960s and early 1970s to replace that form of memory.In most cases, several parallel shift registers would be used to build a larger memory pool known as a "[bit array](https://en.wikipedia.org/wiki/Bit_array "Bit array")". Data was stored into the array and read back out in parallel, often as a [computer word](https://en.wikipedia.org/wiki/Computer_word "Computer word"), while each bit was stored serially in the shift registers.

## D-Flip flop Shift register (course example)

![[Pasted image 20221127150651.png]]


### Serial-In Serial-Out Shift Register (SISO)

- Allows serial input (one bit aftewr the other in a single data line) and produces serial output. 
- Consists of flipflops coupled to the same clock signal (sychronous)
![[Pasted image 20221123094557.png]]
![[Pasted image 20221123094641.png]]
### Serial-In Parallel-Out shift Register (SIPO)
- Sychronous, parralel output, clear input added
- Mainly used to convert serial data into parralel data

![[Pasted image 20221123095021.png]]

## Parralel Load registers
![[Pasted image 20221123100338.png]]

### Parralel in Serial out (PISO)

- Synchronous clock
- Input data is connected to FF via a [[Multiplexers]].

### Parralel in Parralel out (PIPO)



