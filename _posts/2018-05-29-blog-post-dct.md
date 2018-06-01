---
title: 'Discrete consine transform(DCT-II)'
date: 2018-05-30
permalink: /posts/2018/05/DCT/
tags:
  - domain transform
  - DCT
categories:
  - Signal processing
---

### Why use DCT
1. DTFS/FFT (We will not detail into the difference between these two at this moment.) use $e^{jwt}$ as the base. And if $x(t)$ is real and even, $X(\omega)$ is real and even.
2. We are using FFT, we use assume the signal is periodic, we may introduce high frequency at the boundary. So we can build a real periodic signal to handle the boundary issue.
3. Assume the original signal is of length N. Goal is to build a even periodic signal and perform FFT on the new signal.
	* Filp signal along the boundary. Then the start of the signal is the same as the end of the siganl -> solve the boundary issue. -> N becomes 2N.
	* What about the value at $t = 0$? Add 0 between the original signal, so that we construct an even signal. -> 2N becomes 4N.
4. We perform FFT on this 4N signal to get 4N complex values. Then we get N real values for free.
5. It is used in JPEG compression.

### Math equations
 
![dct]({{site.url}}{{site.baseurl}}/assets/images/dct.png)



