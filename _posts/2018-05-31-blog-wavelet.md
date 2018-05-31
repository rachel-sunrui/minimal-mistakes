---
title: 'Wavelet Transform'
date: 2018-05-31
permalink: /posts/2018/05/wavelet/
tags:
  - signal processing
  - domain transform
  - wavelet
---

* We know that wavelet transform comes from STFT by changing a single windowing function to a set of windowing functions.
$$X(t,\omega) = \int_{-\infty}^{\infty}x(t^{\prime})w(t^{\prime} - t)e^{-j\omega t^{\prime} }dt^{\prime} = \int_{-\infty}^{\infty}x(t^{\prime})\phi_{t,\omega} (t^{\prime})dt^{\prime}$$
* Rewrite the function $$\phi_{t,\omega}$$ with two parameters: $$s$$ scale and $$t$$ time shift. We have the wavelet basis
$$\phi_{t,s}(t^{\prime}) = \frac{1}{\sqrt{s}} \phi_m (\frac{t^{\prime} - t}{s})$$ and $$\phi_m$$ is the mother wavelet.
**We can see that this is effectively changing the basis of the transform. Instead of transforming the signal into cosine basis, we find a different sets of basis functions.**
* Unlike Fourier Transform, the basis function only exist in   

### Wavelet basis fucntions
* Orthogonal
* WT is used in JPEG2000 compression.
