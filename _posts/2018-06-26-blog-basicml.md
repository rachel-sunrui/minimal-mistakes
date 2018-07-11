---
title: 'Some basic concepts in CMU 10601'
date: 2018-06-26
permalink: /posts/2018/06/basicml/
tags:
  - naive bayes
  - regression
  - perceptron
  - SVM
categories:
  - Machine Learning
---

### Naive Bayes
* A linear classifier
![nb]({{site.url}}{{site.baseurl}}/assets/images/nb.png)
* Generative model: model $$p(X,y)$$

### Logistic regression
* During the inference, instead of using the sign function in Navie Bayes, use logistic function to make the obj function differentiable.
* Discriminative classifier: model $$p(y|X)$$, maximize it.
* No closed form solution

### Linear regression
* Minimize LSE
* Close form: $$\theta = (X^TX)^{-1}X^Ty$$
	$$\hat{y} = X \theta$$
* Geometric interpretation: $$\hat{y}$$ is the orthogonal projection of $$y$$ into the space spanned by the columns of $$X$$.
* Probabilistic interpretation: LMS is MLE of $$theta$$ with Gaussian noise assumption.

### Perceptron
* Online learning model
* Mistake bound: If data has margin $$\eta$$ and all points inside a ball of radius $$R$$, then Perceprton makes $$\leq (R/ \eta)^2$$ mistakes.
	* Large margin can prevent overfitting
* Can be kernelized

#### Kernel
* $$ K(x,z) = \phi (x) \phi(z)$$
* $$\phi $$ maps lower dimensional data to a higher dimension. $$\phi $$ is implicit (we do not need to know how to exactly map each data point, we only need to know how to map their inner product).
* In fact, the feature space can grow really large quickly. Do not use $$\phi$$ explicitly.
* Function $$K$$ map the inner product to higher dimension.
* K is a kernel iff 
	* K is symmetric
	* Matrix $$K = (K(x_i,x_j))_{i,j=1,\dots,n}$$ is PSD.
* If K1,K2 are kernels, 
	* c1,c2 positive number, c1K1 + c2K2 is also a kernel
	* K1K2 is also a kernel.


### SVM
* Inspired by perceptron, directly search for large margin classifier
* Standard quadratic programming problem
* Hinge loss: $$l(w,x,y) = \max (0, 1 - y*w*x)$$

### Learning theory
* The number of training samples $$m$$ needed is depended on the complexity of H 
	* H is the size of the hypothesis space
	* If H is the class of conjunctions over $$X = {0,1}^n$$. Then $$|H| = 3^n$$ (Every point:0,1,none)
	* If H is infinite, use VC-dimension
	* VCdim of linear separators in $$R^d$$ is $$d+1$$ 
* $$m \propto \frac{1}{2 \eta^2 }[ln(|H| + ln(2/ \delta))]$$ $$\eta$$ error, $$1 - \delta$$ probability of having a small error
* True error and overfitting
![srm]({{site.url}}{{site.baseurl}}/assets/images/srm.JPEG)