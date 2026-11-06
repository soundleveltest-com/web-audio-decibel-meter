# Web Audio Decibel Meter Demo 🎙️

A lightweight, zero-dependency browser decibel meter demonstration built on the standard HTML5 Web Audio API.

## Features

- **Zero dependencies:** Pure vanilla JavaScript, HTML5, and CSS.
- **Client-side only:** Zero audio streaming, recording, or server transmission.
- **Real-time DSP:** Uses `Float32Array` time-domain analysis to calculate instantaneous Root Mean Square (RMS) energy.
- **Natural smoothing:** Exponential moving average prevents jitter.

## How the DSP Works

The meter samples raw PCM audio directly from the device microphone via `createAnalyser()`:

1. **Root Mean Square (RMS):**
   $$\text{RMS} = \sqrt{\frac{1}{N} \sum_{i=1}^{N} x_i^2}$$

2. **Decibel Conversion:**
   $$\text{dBFS} = 20 \times \log_{10}(\text{RMS})$$

3. **Relative Sound Pressure Mapping:**
   A nominal offset of $+100\text{ dB}$ is applied to map relative full-scale digital audio to ambient room decibel values.

## Live Demo

Run the demo instantly on GitHub Pages:
**[https://soundleveltest-com.github.io/web-audio-decibel-meter/](https://YOUR-GITHUB-USERNAME.github.io/web-audio-decibel-meter/)**


## Looking for Calibrated Acoustic Tools?

This repository is a minimal educational reference. For a complete browser acoustic testing suite featuring:

- IEC 61672 frequency weighting curves (**dBA** and **dBC**)
- Continuous equivalent sound levels ($L_{\text{eq}}$, $L_{\text{min}}$, $L_{\text{max}}$)
- Microphone sensitivity calibration
- OSHA and NIOSH noise exposure calculators
- Room acoustic and distance decay tools

Visit the reference application at **[Sound Level Test](https://soundleveltest.com)**.

## License

MIT License. Free to use in your own projects.
