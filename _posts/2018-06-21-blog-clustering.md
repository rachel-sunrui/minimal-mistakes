---
title: 'Clustering'
date: 2018-06-21
permalink: /posts/2018/06/clustering/
tags:
  - k-means
categories:
  - Machine Learning
---

Clustering is aimed at grouping set of objects that have similar "properities". There are many different ways to define the distance for clustering. The famous k-means algorithm is based on the centroid distance model.

### Algorithms
#### Hierarchical clustering
* Based on the distance in a cluster
* Provide a hierarchy of clusters
* Single linkage(minimum)/complete linkage(maximum)/Average linkage
* Partition not unique, user need to choose appropriate clusters.
* Not robust for outliers. May lead to additional clusters or merge other clusters.
* Methods: start with every point in its own cluster -> repeatedly merge the closest two clusters.

#### k-means
* The sum of the distance of all the points to their clusters is the smallest.
* NP-hard (not-solvable in normal time), approximate solution
* Lloyd's method: always converges
* k-means++: instead of initializing the cluster centre randomly, pick them according to the distance from previous centers.
* Polynomial time for smoothed analysis

#### Gaussian mixture models
* Distribution based clustering
* K-means is the hard EM for GMM




	
Hard EM
	1. E-step: Set the latent variables to the values that maximize likelihood, treating parameters as observed. **Hallucinate some data**
	2. M-step: Set the parameters to the values that maximizes the likelihood,treating latent variables as observed.**Standard Bayes Net training**
* Soft EM (The standard EM)
	1. E-step: Create one training example for each possible value of the latent variables. Weight each example according to model's confidence. (Find the posterior for each latent variable, maximize the expectation of the likelihood over the latent variable)
	2. M-step: Set the parameters to the values that maximizes the likelihood.

