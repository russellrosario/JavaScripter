+++
description = "TensorFlow, neural networks"
title = "Machine learning"
draft = false
weight = 200
bref="Machine learning (ML) is the scientific study of algorithms and statistical models that computer systems use to progressively improve their performance on a specific task"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">What is machine learning?</a></h3>
  <div class="example">
    <dl>
    <dt>Is true AI possible?</dt>
    <dd>It is very hard to define a human mind with a such mathematical rigor as it is possible to define a Turing machine. We still do not have a working model of a mouse brain however we have the hardware capable of simulating it. A mouse has around 4 million neurons in the cerebral cortex. A human being has 80-120 billion neurons (19-23 billion neocortical). Thus, you can imagine how much more research will need to be conducted in order to get a working model of a human mind.

You could argue that we only need to do top-down approach and do not need to understand individual workings of every neuron. In that case you might study some non-monotonic logic, abductive reasoning, decision theory, etc. When the new theories come, more exceptions and paradoxes occur. And it seems we are nowhere close to a working model of a human mind.

After taking propositional and then predicate calculus I asked my logic professor:
"Is there any logic that can define the whole set of human language?"
He said:
"How would you define the following?
To see a World in a grain of sand
And a Heaven in a wild flower,
Hold Infinity in the palm of your hand
And Eternity in an hour.
If you can do it, you will become famous."

There have been debates that a human mind might be equivalent to a Turing machine. However, a more interesting result would be for a human mind not to be Turing-equivalent, that it would give a rise to a definition of an algorithm that is not possibly computable by a Turing machine. Then the Church's thesis would not hold and there could possibly be a general algorithm that could solve a halting problem.

Read more on <ins>Godel's Incompleteness theorem</ins>:

* [Minds and machines](http://en.wikipedia.org/wiki/G%C3%B6del%27s_incompleteness_theorems#Minds_and_machines)
* [Godelian arguments](http://en.wikipedia.org/wiki/Mechanism_(philosophy)#G.C3.B6delian_arguments)
</dd>
    <dt>Machine learning vs Statistics</dt>
    <dd>The basic premise of machine learning (ML) is to build algorithms that can receive input data and use statistical analysis to predict an output while updating outputs as new data becomes available. Statistics focuses on quantifying uncertainty by formalizing the relationship between variables and mathematical equations. ML focuses on prediction and classification by using algorithms that learn from data instead of explicity programmed instructions.</dd><br/>
    <dt>Common Applications</dt>
    <dd>
      <ul>
      <li>Image recognition </li>
      <li>Object detection and tracking</li>
      <li>Speech recognition & synthesis</li>
      <li>Algorithmic trading strategies</li>
      <li>Sentiment analysis</li>
      </ul>
    </dd>
      <dt>Supervised vs Unsupervised</dt>
      <ul>
      <li><b>Supervised</b> - Data is labeled and the algorithms learn to predict the output from input data.</li>
      <li><b>Unsupervised</b> - Data is unlabeled and the algorithms learn to find structure from the input data. </dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/learning.png">
    </div>
      <dt>Training and Testing</dt>
      <dd>Separating data into training and testing sets is an important part of evaluating data mining models. Typically, when you separate a data set into a training set and testing set, most of the data is used for training, and a smaller portion of the data is used for testing.</dd>
    </dl>
  </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">Building models</a></h3>
  <div class="example">
    <dl>
      <dt>Tensor</dt>
      <dd>Tensors are a type of data structure used in linear algebra. It is a container which can house data in N dimensions, along with its linear operations. A <ins>tensor processing unit (TPU)</ins> is an AI accelerator application-specific integrated circuit (ASIC) developed by Google specifically for neural network machine learning.</dd>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/tensor.jpg" width="50%">
    </div>
      <dt>Tensorflow</dt>
      <dd>An open source library by Google for building machine learning models.
      <ul>
      <li><b>Tensor math</b> - use linear algebra on tensors</li>
      <li><b>Memory management</b> - the process of controlling and coordinating computer memory and avoiding memory leaks</li>
      <li><b>Loss Functions and Optimizers</b> - A loss function is a method of evaluating how well your algorithm fits the dataset. The optimizer algorithm finds the best parameters (weights) for improving the loss function.</li>
      </ul>
      </dd>
    </dl>
    <dl>
      <dt>Keras</dt>
      <dd>Keras is a minimalist Python library for deep learning that can run on top of TensorFlow. It was developed to make implementing deep learning models as fast and easy as possible for research and development. Using Keras allows for quickly building models by using built-in <ins>estimators</ins>. See below for decision tree on choosing estimator algorithm. </dd><br/>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/ml_map.png">
    </div>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Neural networks</a></h3>
  <div class="example">
  <p>If a machine learning algorithm returns an inaccurate prediction, then an engineer needs to step in and make adjustments. Deep learning structures algorithms in layers to create a neural network that can learn and make intelligent decisions on its own.</p>
    <dl>
      <dt>Feedforward</dt>
      <dd><b>Input layer</b> - will take a representation of the data as a tensor.
      <dd><b>Hidden layer</b> - there can be one or many hidden layers. Each layer has <ins>neuron</ins> unit(s). Every neuron has its own <ins>weighting</ins> for each of the units of the previous layer. After summing the weights and activations, the neuron goes through an <ins>activation function</ins> that squashes the value and produces a new tensor. A <ins>bias</ins> shifts the activation function to the left or right. </dd></dd>
      <dd><b>Output layer</b> - the neurons of this layer also use weights and activation functions. If the shape of the input tensor is different than the output tensor, the weighting has the ability to transform the shape.</dd>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/activation.png">
    </div>
      <br/>
      <dt>Backpropagation</dt>
      <dd>Shorthand for "the backward propagation of errors," since an error is computed at the output and distributed backwards throughout the network’s layers in order for it to learn from mistakes. Error is calculated and then a <ins>gradient descent</ins> optimization algorithm (a differential equation) is used to determine the direction of steepest decline. In order to avoid local minimas, the learning rate should be gradually adjusted higher.</dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/gradient_descent.png" width="50%">
      <figcaption>
Gradient Descent
      </figcaption>
    </div>
    </dl>
    <dl>
      <dt>CNN</dt>
      <dd>CNNs have applications in image and video recognition, recommender systems, image classification, medical image analysis, and natural language processing. The input features are taken in batch wise like a filter. This will help the network to remember the images in parts and can compute operations like converting from RGB to grayscale. The changes in the pixel value will help detecting the edges. </dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/cnn.gif">
    </div>
      <dt>RNN</dt>
      <dd>RNNs are applicable to tasks such as unsegmented, connected handwriting recognition or speech recognition. A class of artificial neural network where connections between nodes form a directed graph along a sequence. This allows it to exhibit temporal dynamic behavior for a time sequence. Unlike feedforward neural networks (connections between the nodes do not form a cycle), RNNs can use their internal state (memory) to process sequences of inputs. </dd>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/rnn.png">
    </div>
      <dt>Unsupervised neural networks</dt>
      <ul>
<li>Self organizing maps - for clustering data and feature detection in higher dimensions</li>
<li>Boltzmann machine - fits a model that will assign a probability to every possible binary vector</li>
<ul>
<li>Used for recommendation systems</li>
</ul>
<li>Autoencoder - encodes and decodes itself</li>
<ul>
<li>The hidden nodes are a bottleneck that extracts the most important features</li>
</ul>
</ul>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/nn_list.png">
    </div>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section4"><a href="#h-Section4">Experimental design</a></h3>
  <div class="example">
  <dl>
    <dt>Bias–variance tradeoff</dt>
    <dd>
    <ul>
    <li><b>Bias</b> is an error from erroneous assumptions in the learning algorithm. High bias can cause an algorithm to miss the relevant relations between features and target outputs <ins>(underfitting)</ins>.</li>
<li><b>Variance</b> is an error from sensitivity to small fluctuations in the training set. High variance can cause an algorithm to model the random noise in the training data, rather than the intended outputs <ins>(overfitting)</ins>.</li>
    </ul>
    </dd>
    <dt>Ensemble learning</dt>
    <dd>Use multiple learning algorithms to obtain better predictive performance than could be obtained from any of the constituent learning algorithms alone. Use confidence intervals and statistical significance tests for comparing ML algorithms.
    <ul>
    <li>P-value for statistical significance</li>
    <li>Chi-squared for normally distributed data</li>
    <li>Pearson and Spearman Correlation</li>
    </ul>
    </dd>
  </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>