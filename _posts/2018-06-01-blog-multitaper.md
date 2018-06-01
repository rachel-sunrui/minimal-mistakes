---
title: 'Multitaper'
date: 2018-06-01
permalink: /posts/2018/06/multitaper/
tags:
  - filtering
  - fft
  - power spectral density
categories:
  - Signal processing
---

The content below is a translation and summary of the wiki page of [Multitaper](https://en.wikipedia.org/wiki/Multitaper).

信号处理领域，Multitaper是用一段有限，来自一个平稳的各态历经的(stationary,ergodic),方差有限的随机过程$$X$$的信号，估计的能量谱其$$S_X$$。这是做能量谱估计的一种方法。

### Motivation
Multitaper的方法克服了传统傅里叶变换的限制。当使用傅里叶变换提取已短信号的频谱信息的时候，我们默认每个傅里叶系数能够可靠地代表每个频率的幅度和相对相位。但是这种假设不一定一直成立。比如，一次实验的数据只是$$X$$的一个带噪声的实现，这不一定能够提供可靠的对于频谱性质的估计。而且，直接用傅里叶变换得出的频谱估计是对真实频谱的一个有偏估计。

把多个实验的信号进行平均可克服这些问题。但是，当数据量很小的时候，我们不想通过平均衰减那些在多个实验之间变化的频率成分。所以Multitaper通过计算同一个实验信号的多个独立的估计来减少估计误差。 信号和每个窗函数相乘之后估计频谱。每个窗函数之间两两正交，因此窗函数提供了一个统计上相互独立的频谱估计。平均各频谱之后可以得到最后的频谱。Slepian或者discrete prolate spheroidal sequences是被经常使用的窗函数。实际应用的时候，可以使用加权平均来平衡高阶窗函数带来的能量损失。

### The Method
考虑一个$$p$$维零均值的平稳随机过程
$$X(t) = [X(1,t),X(2,t),\dots,X(p,t)]^T$$
如果采样间隔为$$\delta t$$，则Nyquist频率是$$f_s = \frac{1}{2\delta t}$$。因此，信号$$l$$和$$m$$之间的multitaper cross-spectral estimator是
![csd]({{site.url}}{{site.baseurl}}/assets/images/multitaper.jpg)
每一个窗函数都能提供良好的频谱泄露保护。有着参数$$W$$和最大阶数$$K$$的Slepian sequences(also called discrete prolate spheroidal sequences or DPSS for short)就可以做到。最大阶数$$K$$要比Shannon number $$2NW\delta t$$小。The quantity 2W defines the resolution bandwidth for the spectral concentration problem and $$ W \in (0,f_{N})$$. When $$l = m$$, we get the multitaper estimator for the auto-spectrum of the $$l$$th channel. In recent years, a dictionary based on modulated DPSS was proposed as an overcomplete [alternative](http://ieeexplore.ieee.org/document/4518243/) to DPSS.