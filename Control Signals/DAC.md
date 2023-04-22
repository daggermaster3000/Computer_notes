![[Pasted image 20221202125026.png]]
A Digital to Analog Converter (DAC) consists of a number of binary inputs and a single output. In general, the **number of binary inputs** of a DAC will be a power of two.

### Types of DACs

#### Weighted Resistor DAC
A weighted resistor DAC produces an analog output, which is almost equal to the digital (binary) input by using **binary weighted resistors** in the inverting adder circuit.
![[Pasted image 20221202125409.png]]
$Rf$ is the feedback resistor (we can control the gain or max output with it). The OP amp maintains a 0V difference between both its inputs.

At the inverting node, we get:
$$
\begin{align}
&\frac{0+V_{R}b_{2}}{2^{0}R}+\frac{0+V_{R}b_{1}}{2^{1}R}+\frac{0+V_{R}b_{0}}{2^{2}R}+\frac{0-V_{0}}{R_{f}}=0 \\ \\
&=>\frac{V_{0}}{R_{f}}=\frac{V_{R}b_{2}}{2^{0}R}+\frac{V_{R}b_{1}}{2^{1}R}+\frac{V_{R}b_{0}}{2^{2}R}
\end{align}
$$
Which is approximately:
$$
V_{0}=b^nb^{n-1}\dots b^1b^0
$$
#### R-2R Ladder DAC

...