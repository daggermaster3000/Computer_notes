![[Pasted image 20221202142556.png]]
The analog to digital converter. 
(It is often coupled to a multiplexer so that different input signals can be measured in sequence by a single ADC.)

**Most important parameters**
- measuring range ($\pm 10 V$)
- resolution (number of bits)
- Conversion time (max sampling rate)
- Linearity #differential #integral
- Offset (value at $0V$ input voltage)
- Time and temperature stability

**Successive approximation**

The ADC performs a binary search through every level of quantization bit by bit (starting with HSB). The bit is initially set to 1 (and the others at 0). If the output from the register is positive keep the bit set at 1 ,else, set it at 0
![[Pasted image 20221202142716.png]]
