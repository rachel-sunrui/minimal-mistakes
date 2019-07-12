---
title: 'Verify the convoliution theorem using Matlab'
date: 2019-04-09
permalink: /posts/2019/4/matlab_fft/
tags:
  - domain transform
categories:
  - Signal processing
  - Coding
---

**When using Matlab to verify "Convolution in time domain is multification in frequency domain", simply doing `fft2` is wrong.**

* `fft2` in defalut is doing circular convolution. (extend with mirroring). If we want to do linear convolution with `fft2`, we need to properly pad the signal. We can use `fft2(X,M,N)` to pad the signal.`M=size(img,1) + size(mask,1)`
* A few ways to show the results are:

```matlab
%% Method1:keep fft2, use circular convolution
im_f = fft2(Y);
ker_f = fft2(G,size(Y,1),size(Y,2));
Iff = im_f.*ker_f;
Iffi = ifft2(Iff);
Yp = padarray(Y,[5,5],'circular'); 
Yd = conv2(Yp,G,'same');
% Remove the padded signal
Yd2 = Yd(4:387,4:515);
figure;imshow(abs(Iffi-Yd2)>1e-6)
%% Method2:use linear conv for fft2
% Discrete Fourier transform
M = size(Y, 1) + size(G, 1);
N = size(Y, 2) + size(G, 2);
Ye = ifft2(fft2(Y, M, N) .* fft2(G, M, N));
Ye = Ye(3:end-3, 3:end-3);  % # Adjust dimensions
figure;imshow(abs(Ye-Yb)>1e-6)
```
