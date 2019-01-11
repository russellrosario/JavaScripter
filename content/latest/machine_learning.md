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
    <dd>Halting problem</dd>
    <dd>Incompleteness Theorem</dd><br/>
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
      <dd>An open source library built by Google that allows you to build your own machine learning models. Doing so requires the following:
      <ul>
      <li><b>Tensor math</b> - Calculate arithmetic operations on tensors</li>
      <li><b>Memory management</b> - the process of controlling and coordinating computer memory and avoiding memory leaks</li>
      <li><b>Loss Functions and Optimizers</b> - A loss function is a method of evaluating how well your algorithm fits the dataset. The optimizer algorithm finds the best parameters (weights) for improving the loss function. A common optimizer algorithm is <ins>Gradient Descent</ins>.</li>
      </ul>
      </dd>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/gradient_descent.png" width="50%">
      <figcaption>
      Gradient Descent
      </figcaption>
    </div>
    </dl>
    <dl>
      <dt>Keras</dt>
      <dd>Keras is a minimalist Python library for deep learning that can run on top of TensorFlow. It was developed to make implementing deep learning models as fast and easy as possible for research and development. Using Keras allows for quickly building models by using built-in <ins>estimators</ins>. See below for help on determining how to select an estimator. </dd><br/>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/keras.svg">
    </div>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Neural networks</a></h3>
  <div class="example">
  <p>If a machine learning algorithm returns an inaccurate prediction, then an engineer needs to step in and make adjustments. Deep learning structures algorithms in layers to create a neural network that can learn and make intelligent decisions on its own.</p>
    <dl>
      <dt>Layers</dt>
      <dd>Consists of inputs, “hidden layers”, and outputs. Hidden layers do not necessarily need to be a blackbox, but modifying them will involve tensor calculations.</dd>
      <dd>Input layer</dd>
      <dd>Hidden layers</dd>
      <dd>Outputs</dd><br/>
      <dt>Activation function</dt>
      <dd>TBD </dd>
      <dt>Backpropagation</dt>
      <dd>TBD </dd>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/nn.png">
    </div>
    </dl>
    <dl>
      <dt>CNN</dt>
      <dd>The input features are taken in batch wise like a filter. This will help the network to remember the images in parts and can compute operations like converting from RGB to grayscale. The changes in the pixel value will help detecting the edges and images can then be classified into different categories. </dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/cnn.gif">
    </div>
      <dt>RNN</dt>
      <dd>A class of artificial neural network where connections between nodes form a directed graph along a sequence. This allows it to exhibit temporal dynamic behavior for a time sequence. Unlike feedforward neural networks (connections between the nodes do not form a cycle), RNNs can use their internal state (memory) to process sequences of inputs. </dd>
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
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section4"><a href="#h-Section4">Experimental design</a></h3>
  <div class="example">
  <dl>
    <dt>Computation</dt>
    <dd>Hyperparameters - learning rate</dd>
    <dt>Testing</dt>
    <dd>AB testing, Ensemble learning, </dd>
    <dt>Bias</dt>
    <dd>Bias/Variance</dd>
    <dt>Significance</dt>
    <dd>T-statistic and low P-value</dd>
    <dd>Chi-squared (normal distribution)</dd>
    <dd>Pearson or Spearman (correlation)</dd>
  </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>