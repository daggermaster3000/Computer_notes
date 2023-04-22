Counters and dividers can be used to provide a clock or divide frequency. Initial clock is a quartz then we get seconds. 

### Asynchronous counter (Ripple counter)

Asynchronous counters are those whose output is free from the clock signal. Because the flip flops in asynchronous counters are supplied with different clock signals, there may be delay in producing output. Done with master slave JK flip flops (or else no delay is implemented and we get a shift register)

![[Pasted image 20221123104226.png]]

**A master slave NAND Flip Flop**
![[Pasted image 20221126174835.png]]
**Implemented**
![[Animation.gif]]

>**Asynchronous counters** suffer from propagation delay (outputs dont change at the same time)

### Sychronous counter
The external clock is connected to every flip flop clock input. So the output occurs with no ripple effect (or propagation delay). 
![[Pasted image 20221127144746.png]]
**Implementation**
![[Sync_counter.gif]]

