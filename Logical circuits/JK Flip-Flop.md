This circuit solves the problems of SR Flip Flops.

	- the Set = 0 and Reset = 0 condition (S = R = 0) must always be avoided
	- if Set or Reset change state while the enable (EN) input is high the correct 
        latching action may not occur

The **JK flip flop** is basically a gated SR flip-flop with the addition of a clock input circuitry that prevents the illegal or invalid output condition that can occur when both inputs S and R are equal to logic level “1”. Due to this additional clocked input, a JK flip-flop has four possible input combinations, “logic 1”, “logic 0”, “no change” and “toggle”. The symbol for a JK flip flop is similar to that of an _SR Bistable Latch_ as seen in the previous tutorial except for the addition of a clock input.

![[Pasted image 20221116140042.png]]
![[Pasted image 20221116133000.png]]
#### Truth table
![[Pasted image 20221116133203.png]]
![[Pasted image 20221116140111.png]]

### [[Master-Slave JK Flip-Flop]]

The master-slave flip-flop eliminates all the timing problems by using two SR flip-flops connected together in a series configuration. One flip-flop acts as the “Master” circuit, which triggers on the leading edge of the clock pulse while the other acts as the “Slave” circuit, which triggers on the falling edge of the clock pulse. This results in the two sections, the master section and the slave section being enabled during opposite half-cycles of the clock signal.

![[Pasted image 20221116133236.png]]

