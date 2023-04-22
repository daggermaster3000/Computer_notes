https://www.electronics-tutorials.ws/logic/logic_9.html
Deja what is a buffer ? 
==In computer science, a data buffer is a region of a memory used to temporarily store data while it is being moved from one place to another. Typically, the data is stored in a buffer as it is retrieved from an input device or just before it is sent to an output device==

### The Digital buffer

The digital buffer is the logic gate opposite of an inverter (Not Gate). 
The “Buffer” performs no inversion or decision making capabilities (like logic gates with two or more inputs) but instead produces an output which exactly matches that of its input. In other words, a digital buffer does nothing as its output state equals its input state.

$\text{Q is true, only when A is true}$

In other words, the output ( Q ) state of a buffer is only true (logic “1”) when its input A is true, otherwise its output is false (logic “0”).
![[Pasted image 20221123101335.png]]

**What's the point ?**
Why not just use a piece of wire instead, and that’s a good point. But a non-inverting Digital Buffer does have many uses in digital electronics with one of its main advantages being that it provides digital amplification.

_Digital Buffers_ can be used to isolate other gates or circuit stages from each other preventing the impedance of one circuit from affecting the impedance of another. A digital buffer can also be used to drive high current loads such as transistor switches because their output drive capability is generally much higher than their input signal requirements. In other words buffers can be used for power amplification of a digital signal as they have what is called a high “fan-out” capability. 

**Fan Out**
The fan-out is the number of parallel loads that can be driven simultaneously by one digital buffer of logic gate. Acting as a current source a buffer can have a high fan-out rating of up to 20 gates of the same logic family.

### The Tri-State Buffer

![[Pasted image 20221123102157.png]]

A Tri-state Buffer can be thought of as an input controlled switch with an output that can be electronically turned “ON” or “OFF” by means of an external “Control” or “Enable” ( EN ) signal input. This control signal can be either a logic “0” or a logic “1” type signal resulting in the Tri-state Buffer being in one state allowing its output to operate normally producing the required output or in another state were its output is blocked or disconnected.

Then a tri-state buffer requires two inputs. One being the data input and the other being the enable or control input.

In the course we use the **active low inverting** tri state buffer. 

![[Pasted image 20221123102441.png]]

**Hi-Z** means disconnected from the circuit (High impedance (very low amount of current can pass through the node)).


### Uses in data Bus
So digital buffers are available in the tri-state form that allows the output to be effectively switched-off producing a high impedance state (Hi-Z) equivalent to an open circuit. They allow multiple logic devices to be connected to the same wire or bus without damage or loss of data.
![[Pasted image 20221123103516.png]]
For example, suppose we have a data line or data bus with some memory, peripherals, I/O or a CPU connected to it. Each of these devices is capable of sending or receiving data to each other onto this single data bus at the same time creating what is called a **contention**.

**Contention** occurs when multiple devices are connected together because some want to drive their output high and some low. If these devices start to send or receive data at the same time a short circuit may occur when one device outputs to the bus a logic “1”, the supply voltage, while another is set at logic level “0” or ground, resulting in a short circuit condition and possibly damage to the devices as well as loss of data.

Digital information is sent over these data buses or data highways either serially, one bit at a time, or it may be up to eight (or more) wires together in a parallel form such as in a microprocessor data bus allowing multiple tri-state buffers to be connected to the same data highway without damage or loss of data as shown.

![[Pasted image 20221123103618.png]]

The **Tri-state Buffer** can be used to isolate devices and circuits from the data bus and one another. If the outputs of several Tri-state Buffers are electrically connected together Decoders are used to allow only one set of Tri-state Buffers to be active at any one time while the other devices are in their high impedance state.

### Uses with Binary decoder

![[Pasted image 20221123103807.png]]


