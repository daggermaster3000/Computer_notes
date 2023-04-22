#integral
### Integral nonlinearity (INL)
INL is a measure of performance in DAC and ADC converters.
![[Pasted image 20221202135910.png]]
The ideal transfer function of a DAC or ADC is a straight line. The INL measurement depends on what line is chosen as ideal. One common option is the line that connects the endpoints of the transfer function, in other words, the line connecting the smallest and largest measured input/output value
**DACs**
![[Pasted image 20221202140114.png]]
Measure of the deviation between the ==ideal output value== and the ==actual measured output value== for a certain input code. The INL of a code ${\displaystyle c}$ of a DAC with ${\displaystyle N_{c}}$ output codes is defined as the absolute value of the difference of the real output voltage minus the ideal value:
$$
{\displaystyle \mathrm {INL} _{c}=\left|V_{\mathrm {o,ideal} }(c)-V_{\mathrm {o,real} }(c)\right|=\left|(V_{\mathrm {o,max} }-V_{\mathrm {o,min} }){\frac {c}{N_{c}-1}}-V_{\mathrm {o,real} }(c)\right|}
$$

where ${\displaystyle V_{\mathrm {o,max} }}$ and ${\displaystyle V_{\mathrm {o,min} }}$ are the maximum and minimum ideal output voltages of the DAC.

**ADCs**
![[Pasted image 20221202140127.png]]
it is the deviation between the ==ideal input threshold value== and the ==measured threshold level== of a certain output code.

#differential 
### Differential non linearity (DNL)
![[Pasted image 20221202140817.png]]
It is a term describing the deviation between two analog values corresponding to adjacent input digital values. It is an important specification for measuring error in a [digital-to-analog converter](https://en.wikipedia.org/wiki/Digital-to-analog_converter "Digital-to-analog converter") (DAC); the accuracy of a DAC is mainly determined by this specification. Ideally, any two adjacent digital codes correspond to output analog voltages that are exactly one [Least Significant Bit](https://en.wikipedia.org/wiki/Least_significant_bit "Least significant bit") (LSB) apart.
![[Pasted image 20221202140933.png]]
Upper is better representation
$$
{\displaystyle {\text{DNL(i)}}={{V_{\text{out}}(i+1)-V_{\text{out}}(i)} \over {\text{ideal LSB step width}}}-1}
$$
