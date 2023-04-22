## Control options for input and output

### Polling (pull|polled I/O)
The computer regularly queries the process and retrieves data.
- Advantages: 
	- Easy to implement
	- Computer in control
	- High freq. polling leads to fast response (requires lots of computing power)
- Disadvantages:
	- Poor utilization of CPU resources
	- Signals can get lost
	- Difficult to control sevral processes at once (shit at multitasking)

### Interrupts (push)
The process notifies the computer that somethiong happend. The computer interrupts its work to serve the process
- Advantages:
	- Fast response possible (without burdenong the CPU)
	- Good for multitasking
- Disadvantages:
	- Hard to implement
	- needs an ==interrupt handler== or ==os driver==

### Direct memory access (DMA)
- Transport of the data ==without CPU==. 
- A special DMA controller takes over the control of the memory bus and transfers the data between memory and periphery. 
- Fast data transfer possible without CPU load.

### Programmed data transmission
- The ==CPU== takes care of the data transfer. 
- Special I/O commands or memory mapped I/O possible.