The SET/RESET flip flop is a 1-bit memory bistable device. 

- SET produces output 1.
- RESET produces output 0, or reverts back to original state.
- $Q_{v}$ is the previous state of Q
- **Invalid** condition $S=0, R=0$ because we then get $Q= \bar{Q}=1$. The flip flop loses control of $\bar{Q}$ and $Q$ (if $S=1, R=1$ ) (because of gate delay one nand will send the signal before thus switching off the other). This is known as the metastable state. The [[JK Flip-Flop]] solves this problem.

#### Truth table
![[Pasted image 20221116141114.png]]

![[Pasted image 20221116105715.png]]
![[Pasted image 20221116131218.png]]
#### OR + NOT 
![[Pasted image 20221116104958.png]]
#### NOR
![[Pasted image 20221116105017.png]]
#### NAND
![[Pasted image 20221116105044.png]]
#### Symbols
![[Pasted image 20221116105121.png]]

## Use as switch debouncing
Switch may bounce causing multiple inputs that each act as signals. Eventually we'll end up with not our intended output state.
![[Pasted image 20221116142642.png]]
We can use SR flip flops in the following circuit to solve this problem. 
![[Pasted image 20221116143218.png]]
When the switch is activated, the output state is directly retained.