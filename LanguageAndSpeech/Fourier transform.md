22092313:04
Status:  #LanguageAndSpeech
Tags: 

# Fourier transform
*Read **working of the ear** in reading materials*

- **The forward transform** (or **analysis integral**) extracts the frequency information from a time signal 
	$$X_k = f_0 \int _{0}^{T_0}x(t)e^{-i2\pi f_0 k t}dt$$

- **The inverse transform** (or **synthesis integral**) creates the time-domain signal from its spectral information.
	$$x(t) = \Sigma_{-\infty}^{\infty}X_k e^{i2\pi f_0 k t}$$

**Fourier series** describe a composite periodic wave in a specific time window  
using a sum of complex exponential signals where the frequencies are all multiples of the fundamental frequency.
$$x(t) = A_0 + \sum_{k=1}^{N}\cos (2 \pi f_kt+\phi_k)$$
the onset and offset discontinuities are manifest as “**spectral splatter**,” which can extend a long way up or down in frequency, and are therefore “audible” to our hypothetical 4-kHz cell.
This spectral splatter, which occurs if we cut a sound wave into arbitrary chunks, can also plague any attempt at spectrographic analysis.

---
# References