---
published: false
---
# Generative Models


## Learning Goals


<!-- MarkdownTOC autolink=true autoanchor=true bracket=round -->

- [Introduction](#introduction)
- [Generative Adversarial Networks](#generative-adversarial-networks)
    - [Variational Autoencoders](#Variational-Autoencoders)
    - [DCGAN](#DCGAN)
    - [Extensions](#extensions)


<a name="introduction"></a>
# introduction
in this tutorial we going to learn about Generative Models and implement some of them

what is Generative Model:

In probability and statistics, a generative model is a model for randomly generating observable data values, typically given some hidden parameters. It specifies a joint probability distribution over observation and label sequences. Generative models are used in machine learning for either modeling data directly (i.e.https://arxiv.org/abs/1312.6114, modeling observations drawn from a probability density function), or as an intermediate step to forming a conditional probability density function. A conditional distribution can be formed from a generative model through Bayes' rule.

<a name="generative-adversarial-networks"></a>
# generative Adversial Network

Generative Adversarial Networks ([GAN](https://arxiv.org/abs/1406.2661)) is a framework for training generative models that use deep neural networks. The approach simultaneously trains a generative model alongside an adversarial discriminative model. The discriminative model tries to determine whether a sample comes from the true data distribution or from the generative model, while the goal of the generative model is to fool the discriminative model.

![GAN](http://www.kdnuggets.com/wp-content/uploads/generative-adversarial-network.png)

 ## Generative vs Discriminative Models

We describe the differences between discriminative and generative models. Suppose we have some data and some signal , with joint distribution . A discriminative model is a mapping from a value of to a signal . It does not care about the distribution , only that there exist some boundaries separating the 's that map to a certain value of and the 's that map to a different value of . On the other hand, a generative model tries to directly learn the distribution . In doing so, it does not explicitly learn boundaries separating different signals, but instead learns the entire distribution, which can be used to infer about the signals .

The main advantage of a generative model over discriminative models is the ability to generate samples from the distribution (supposing that the generative model is able to perfectly model the distribution). So while discriminative models are simpler to train, and typically performs better on most supervised tasks, generative models are more expressive as it approximates the true data distribution.

Below, we discuss a framework that uses neural networks to construct a generative model. Neural networks have been shown to perform spectacularly as discriminative models, usually in a classification setting where the inputs are high dimensional. GAN is a method that takes advantage of the performance of neural networks as discriminative models to aid in the training of a generative neural network.
