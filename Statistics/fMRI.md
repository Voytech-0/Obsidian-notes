22051010:07
Status:  #IntroToBrain
Tags: 

# fMRI
**functional Magnetic Resonance Imaging**

- Sending magnetic pulses affects the spins of protons
- Relaxation times differ between tissues 
- In functional MRI we are looking for changes between oxygenation of blood
- BOLD (blood oxygen-level dependent) signal
- Time resolution is around 1-2 or even 7s. 
- The amount of glucose in blood changes based on the activity of brain regions.

**TR** - repetition time - time elapsing between scans
To find the voxels correlated with our signal we need to follow many steps:
1. Images are realigned (different timing)
2. Spatial normalisation to standard brain space - Each brain is different but we need to standardise the image
3. Smoothing data - blurring anatomical differences
4. Doing statistics - First estimating sources of noise such as participant motion
5. Combining statistical maps with anatomical information

Hemodynamic response function (HRF)

---
# References