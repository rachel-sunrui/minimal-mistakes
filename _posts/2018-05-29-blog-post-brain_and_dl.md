---
title: 'Reading summary for The Brain vs Deep Learning -- from Tim Dettmer '
date: 2018-05-26
permalink: /posts/2018/05/brainvsdl/
tags:
  - deep learning
  - neuroscience
---

**Original post: <http://timdettmers.com/2015/07/27/brain-vs-deep-learning-singularity/>**

This article compares the biological structure of a brain to a deep learning network and proposed: 
* Single neuron performs more like a convolutional network instead of a perceptron. 
* Currently many estimations of the brain computational power understimate the power becasue they did not include factors like brain connections information processing, backpropagation and learning of neurons and the dynamic DNA changes in neurons.
* Supercomputers will not reach the computation power of the brain in the near future considering the limitations like semiconductor fabrication or the bottlenecks come from DL like memory and network bandwidth.

Below is some interesting points from the blog, note that some of the sentenses maybe directly referenced from the original post:
## Compare a neuron to a neural net
* Axon terminal and synapses -- input layer into a convolutional net.
* The combination of 
	* the amount of neurotransmitters released
	* the number of receptors for a given neurotransmitter
	* how many neurotransmitters actually make it into a fitting protein on the synapse
-- weight parameter in a densely (fully) connected layer of a neural network.*(So in his point, pre-synaptic potential is the input and goes through a dense layer and post-synaptic potential is the output)*
* A dendritic spine is a small mushroom-like structure on to which the synapse is attached. These dendritic spines can store electric potential and have their own dynamics of information processing*(whose influence on computational power is usually left out in the estimation)*.The size and shape of the mushroom-like dendritic spine corresponds to its behavior. 
* Due to the introduction of dendritic spikes into computational models of neurons, the complexity of a single neuron has become very similar to a convolutional net with two convolutional layers. 
* After a dendritic spike, the opening of voltage-gated channels greatly amplifies the signals in all neighboring branches within the dendritic tree. Thus a dendritic spike may heighten the electrochemical levels in neighboring dendrites to a level which is more similar to the maximum input — this effect is close to max-pooling.
* *Back-propagation is also in a single neuron.* During neural back-propagation — that is when the action potential travels from the cell body back into the dendritic tree — the signal cannot backpropagate into the dendritic branch where the dendritic spike originated because these are “deactivated” due to the recent electrical activity. Thus a clear learning signal is sent to inactivated branches. At first this may seem like the exact opposite from the backpropagation used for max-pooling, where everything but the max-pooling activation is backpropagated. However, the absence of a backpropagation signal in a dendrite is a rare event and represents a learning signal on its own. Thus, dendrites which produce dendritic spikes have special learning signals just like activated units in max-pooling.
* *Neuron DNA changes dynamically.* Does every cell in your body has (almost) the same DNA? Generally, this is true for most cells, but not true for most neurons. Neurons will typically have a genome that is different from the original genome that you were assigned to at birth. Neurons may have additional or fewer chromosomes and have sequences of information removed or added from certain chromosomes. It was shown, that this behavior is important for information processing and if gone awry, this may contribute to brain disorders like depression or Alzheimer’s disease. Recently it was also shown, that neurons change their genome on a daily basis to improve information processing demands.
* In the LNP model, the refractory period of an action potential is modeled as an inhomogeneous Poisson process which has a Poisson distribution. Generally, this whole process is very similar to dropout used in deep learning which uses a uniform distribution instead of a Poisson distribution; thus this process can be viewed as some kind of regularization method that the brain uses instead of dropout.
* One *great disparity* is that the dropout in the brain works with respect to all inputs, while dropout in a convolutional network works with respect to each single unit.

## Learning and memory in the brain
* Brain adjusts synapses with some sort of reinforcement learning algorithm in order to learn new memories. 
* The advantage about convolution is that we can use methods like maximum-likelihood estimation with backpropagation to learn parameters which lead to meaningful representations which are akin to memories (just like we do in convolutional nets). This is exactly akin to the LNP model with its convolution operation.
* The LNP model is also justified in that it is actually possible to learn parameters which yield meaningful memories (where with memories I mean here distributed representations like those we find in deep learning algorithms).
