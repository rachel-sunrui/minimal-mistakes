---
title: 'Some basic concepts in CMU 10601'
date: 2018-06-26
permalink: /posts/2018/06/basicml/
tags:
  - naive bayes
categories:
  - Machine Learning
---

### Naive Bayes
* A linear classifier
![nb]({{site.url}}{{site.baseurl}}/assets/images/nb.png)
* Generative model: model $$p(X,y)$$

### Logistic regression
* During the inference, instead of using the sign function in Navie Bayes, use logistic function to make the obj function differentiable.
* Discriminative classifier: model $$p(y | X)$$, maximize it.
* No closed form solution

### Linear regression
* Minimize LSE
* Close form: $$\theta = (X^TX)^{-1}X^Ty$$
$$\hat{y} = X \theta$$
* Geometric interpretation: $$\hat{y}$$ is the orthogonal projection of $$y$$ into the space spanned by the columns of $$X$$.
* Probabilistic interpretation:LMS == MLE of $$theta$$ with Gaussian noise assumption.

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
	* Matrix $$K = (K(x_i,x_j)){i,j=1,\dots,n}$$ is PSD.
* If K1,K2 are kernels, 
	* c1,c2 positive number, c1K1 + c2K2 is also a kernel
	* K1K2 is also a kernel.


### SVM
* Directly search for large margin classifier
* 
