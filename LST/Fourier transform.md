22092313:04
Status:  #LanguageAndSpeech
Tags: 

# Fourier transform
Same week as [[Sound perception]]
$$A_{total}= A\cos(2\pi  f t + \phi)$$

- **The forward transform** (or **analysis integral**) extracts the frequency information from a time signal 
	- We have a signals, and we want to know its frequency.
	$$X_k = f_0 \int _{0}^{T_0}x(t)e^{-i2\pi f_0 k t}dt$$

- **The inverse transform** (or **synthesis integral**) creates the time-domain signal from its spectral information.
	$$x(t) = \Sigma_{-\infty}^{\infty}X_k e^{i2\pi f_0 k t}$$

**Fourier series** describe a composite periodic wave in a specific time window  
using a sum of complex exponential signals where the frequencies are all multiples of the fundamental frequency.
$$x(t) = A_0 + \sum_{k=1}^{N}\cos (2 \pi f_kt+\phi_k)$$
the onset and offset discontinuities are manifest as “**spectral splatter**,” which can extend a long way up or down in frequency, and are therefore “audible” to our hypothetical 4-kHz cell.
This spectral splatter, which occurs if we cut a sound wave into arbitrary chunks, can also plague any attempt at spectrographic analysis.

We only use *odd harmonics*, as even harmonics do not line up 

---

**Hann smoothing** and Hann function
	Hann function is applied to smooth the end of sound intervals. ![[Pasted image 20221028175347.png|300]]

**Mel scale** 
	Relates perceived frequency to its actual measured frequency
	![[Pasted image 20221028175628.png|400]]![[Pasted image 20221028175726.png|400]]

---
# References