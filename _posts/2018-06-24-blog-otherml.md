---
title: 'Some less popular concepts in CMU 10601'
date: 2018-06-24
permalink: /posts/2018/06/otherml/
tags:
  - semi-supervised learning
  - active learning
  - boosting
categories:
  - Machine Learning
---

* Semi-supervised learning: mixing labeled and unlabeled data as training data (no query for labels during training); based on the belief that data has the same structure.
	* Semi-supervised SVM: find a labeling of the unlabeled sample and $$w$$ s.t. $$w$$ separates both labeled and unlabeled data with maximum margin.
	* Co-training: different features are consistently representing one label. Train multiple classifiers. Use the labeling result of one classifier to help the training of others.
	* Graph-based methods: construct a graph with edges between very similar examples. Examples with strong edges should have same labels.

* Active learning:
	* use fewer labeled examples
	* algorithm chooses which examples to be labeled
	* can have sampling bias, need to be careful when choosing query strategy: like version space method.

* Boosting:
	* Combine several weak learners to produce an overall high-accuracy predictor.
	* Steps: apply 1st weak learner -> find the most easily classified examples for the 2nd rule of thumb -> take (weighted) majority vote of all learners
	* Adaptive boosting: find the weight for the majority vote
		* Training error drops exponentially in T(number of rounds/weak learners)
		* In experiments, test error does not increase with training rounds(in constrast with Occam's razor). We need to also consider the classification confidence.