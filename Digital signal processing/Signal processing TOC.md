**TOC**
[[Signal processing TOC#Analog vs Digital]]
- [[Fourier transform]]
	- [[Fundamental]]
	- [[continous signals]]
	- [[sampled signals]]
	- [[DFT]]
- [[Description of linear systems]]
- [[Acoustic resonator]]

**Resumey**
![[Pasted image 20221212163308.png]]
The central processing of the data can be taken over by a conventional processor or for fast applications by a so-called DSP ( Digital Signal Processor, e.g. TMS 320, ADSP 218x, DSP 560x ). These are processors whose instruction set is specially adapted to the needs of digital signal processing and therefore achieve higher processing speeds. This is particularly important in real-time applications where the output of the processed signal must be synchronous with the input signal, i.e. the data must be able to be processed exactly as fast as it is generated.

# Analog vs Digital

The required processing speed determines the application range. 
![[Pasted image 20221213145920.png]]

## Advantages of DSP

- Better signal to noise ratio (determined by the number of bits as well)
- No mismatch
- Losless data transmission
- Predictability and reproducibility
- [Adaptive filters](https://en.wikipedia.org/wiki/Adaptive_filter) are feasible
- Can be extended to multi-dimensional quantities (image processing) (not only time varying signals)
- **Techniques:** [[Fourier transform]], [[Laplace transform]], z-transform, impulse response, step response 

## Application examples

- DVD,MP3,RADIO
- Braking systems, GPS
- Image editing, object tracking
- Ultrasound equipement, RMN, Tomography
- Seismology

## Alias frequencies

When nyquist not met original frequency $f$ aliased to $f-fs$
