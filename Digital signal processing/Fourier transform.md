```toc
```

## Basics
Any periodic signal with frequency $f=1/T$ can be written as a sum of harmonic oscillations of frequencies $f, 2f, 3\mathbf{f}\dots$

**Intuition 1**
We take a signal to be decomposed and wrap it around a circle in a 2d (complex) plane with a certain wrapping frequency. Next we can calculate the center of mass of the signal (relative to the x axis (the real part)) by doing an average and this gives us how much the wrapping frequency contributes to the signal.

**Equation**
$x(t)$ is the signal to be processed/input function

$$
\begin{align}
X(\omega)= \int_{-\infty}^{\infty} x(t)e^{-i\omega t} \,  \, dt = \int_{-\infty}^{\infty} x(t) \cos(\omega t) dt- i \int_{-\infty}^{\infty} x(t) \sin(\omega t) dt
\end{align}
$$
Once the integral is computed we end up with a transfer function and we compute the magnitude for given $\omega$ to get our peaks at these $\omega$. ($\omega = 2\pi \times f$) (and $f$ is the frequency)

==Note:==
- Euler's formula: $\cos(\phi)+i \sin(\phi) = e^{i \phi}$ makes us walk around the unit circle $\phi$ times
- The function spits out a real and complex component. The real part is the intensity of sine of the computed frequency and the imaginary is the contribution of the cosine component. We can get both in a power spectrum 

**Facts**
- When $\omega = 0$, the $e$ term goes to $1$ and we get the integral/area under the curve of the input function

## Continous signals

The Fourier transform of **periodic** signals contains **discrete** frequencies, while **aperiodic** signals lead to **continuous** spectra
![[Pasted image 20221214144239.png]]

## Sampled signals

In data acquisition, the signal is acquired at uniform time intervals $T$. A multiplation of the signal to be sampled by a sampling function can describe this:
$$
\begin{align}
x^*(t) = x(t)w(t)
\end{align}
$$

$$
\begin{align}
w(t)=\sum^{K-1}_{j=0}\delta(t-jT)
\end{align}
$$
Where, 
- $K$ defines the size of the window
- $\delta(t-jT)$ is the [[delta function]]

So we have $x(t)$:
![[Pasted image 20221214150745.png]]

And we have $w(t)$:
![[Pasted image 20221214150814.png]]

By multipling the two we get $x^*(t)$:
![[Pasted image 20221214151227.png]]

We now want to get the frequencies from this sampled signal. Enter 

**Convolution** #convolution
If we know the Fourier transforms of the continuous signal X and the window function W then we can determine the Fourier transform of the sampled signal by convolution.

$$
\begin{aligned}
X^*(\omega) & =\int_{-\infty}^{+\infty} x(t) w(t) e^{-i \omega t} d t \\

\end{aligned}
$$
And, 
$$
\begin{aligned}
x(t)=\frac{1}{2 \pi} \int_{-\infty}^{+\infty} X(\eta) e^{i \eta t} d \eta & \\
W(\omega)=\int_{-\infty}^{+\infty}{ }_{w(t) e^{-i \omega t} d t} 
\end{aligned}
$$
So plugging in we get:
$$
\begin{aligned}
& =\int_{-\infty}^{+\infty} \frac{1}{2 \pi} \int_{-\infty}^{+\infty} X(\eta) e^{i \eta t} d \eta w(t) e^{-i \omega t} d t \\
& =\frac{1}{2 \pi} \int_{-\infty}^{+\infty} X(\eta) \int_{-\infty}^{+\infty} w(t) e^{-i(\omega-\eta) t} d t d \eta \\
& =\frac{1}{2 \pi} \int_{-\infty}^{+\infty} X(\eta) W(\omega-\eta) d \eta

\end{aligned}
$$

## Discrete fourier transform

![[Pasted image 20221214155828.png]]
A direct/naive approach to calculating a DFT will give you an _O_(_N_2) algorithm (doubling the number of samples will quadruple the length of time taken to complete the algorithm). Fortunately, there are a family of algorithms known as fast Fourier transforms (FFTs) that are _O_(_N_ log _N_), which make DFTs on very long samples computationally feasible.
![[Pasted image 20221214160428.png]]

#### Overview of the convolution and sampling rate
As mentioned previously, we can either multiply the $h(t)$ sample by the $\Delta(t)$ sampling function then fourier transform to get to the frequency domain. Or we can fourier transform each of them separately and then convolute them.
![[Pasted image 20221221172725.png]]
If the sampling rate doesnt meet the nyquist criterion , there will be emergence of alias frequencies.
![[Fourier transform 2022-12-21 15.22.52.excalidraw|900]]

#### View with sampling window (the convolution)

![[Fourier transform 2022-12-21 17.39.50.excalidraw|1000]]

![[Pasted image 20221221151412.png]]
