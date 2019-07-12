title: 'Image data preprocessing for neural networks'
date: 2019-05-31
permalink: /posts/2019/5/preprocesssing/
categories:
  - Machine learning
---

<!-- The caregories I used:
  - Tools
  - Coding
  - Neuroscience
  - Machine learning
  - Image processing
  - Signal processing -->


* We treat each pixel in the image as a variable. We want to make the mean and std of each pixel similar cross all training samples (cross the samples in a batch). So we need to do normalization over each pixel. (Not over one image.)
* There are several ways to do the normalization:
    * ```(x - x.min()) / (x.max() - x.min())```
    * ```2*(x - x.min()) / (x.max() - x.min()) - 1```
    * ```(x - x.mean()) / x.std()```