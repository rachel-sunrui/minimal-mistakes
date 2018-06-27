---
title: 'Clustering'
date: 2018-06-21
permalink: /posts/2018/06/clustering/
tags:
  - k-means
  - Gaussian mixture models
  - hierarchical clustering
  - EM
categories:
  - Machine Learning
---

Clustering is aimed at grouping set of objects that have similar "properities". There are many different ways to define the distance for clustering. The famous k-means algorithm is based on the centroid distance model.

### Hierarchical clustering
* Based on the distance in a cluster
* Provide a hierarchy of clusters
* Single linkage(minimum)/complete linkage(maximum)/Average linkage
* Partition not unique, user need to choose appropriate clusters.
* Not robust for outliers. May lead to additional clusters or merge other clusters.
* Methods: start with every point in its own cluster -> repeatedly merge the closest two clusters.

### k-means
* The sum of the distance of all the points to their clusters is the smallest.
* NP-hard (not-solvable in normal time), approximate solution
* Lloyd's method: always converges
* k-means++: instead of initializing the cluster centre randomly, pick them according to the distance from previous centers.
* Polynomial time for smoothed analysis

### Gaussian mixture models
* Distribution based clustering
	
#### Hard EM
* K-means is the hard EM for GMM
1. E-step: Go through every possibe labels for each data point, set the labels (latent variables) to the values that maximize likelihood.
2. M-step: Treat the label as known. MLE training for the parameters.

#### Soft EM (The standard EM)
1. E-step: For each example, each point has a probability of belonging to certain group, which means each example has #groups values representing its probability of belonging to this group. (Find the posterior for each latent variable, maximize the expectation of the likelihood over the latent variable)
2. M-step: Set the parameters to the values that maximizes the likelihood.

