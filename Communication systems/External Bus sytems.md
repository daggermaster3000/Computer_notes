> A bus is a communication system where the data can reach different devices on the same transmission system

![[Pasted image 20221220165127.png]]
Asynchronous means the receiver must acknowledge first. In practice the speed is determined by the connected devices.

### What to select when

**Internal buses** 
Small experiments with few I/O

**GPIB0**
Medium experiments, Low data bandwith, lots of devices work with it oput of the box

**VME Bus**
Large applications, Very large data bandwith, software must be scalable

**CAMAC,FASTBUS**
Nuclear and particle physics

![[Pasted image 20221111134831.png]]
Due to impedance variations, high frequency signals are modulated