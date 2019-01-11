+++
description = "TensorFlow, neural networks"
title = "Machine learning"
draft = false
weight = 200
bref="Machine learning (ML) is the scientific study of algorithms and statistical models that computer systems use to progressively improve their performance on a specific task"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section0"><a href="#h-Section0">Intro</a></h3>
  <div class="example">
    <dl>
    <dt>Is true AI possible?</dt>
    <dd>Halting problem, Incompleteness Theorem</dd>
    <dt>Machine learning vs Statistics</dt>
    <dd>The basic premise of machine learning is to build algorithms that can receive input data and use statistical analysis to predict an output while updating outputs as new data becomes available.</dd>
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
  </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Tensors</a></h3>
  <div class="example">
    <dl>
      <dt>Tensor</dt>
      <dd>Tensors are a type of data structure used in linear algebra. It is a container which can house data in N dimensions, along with its linear operations. TPUSs</dd>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/tensor.jpg">
    </div>
      <dt>Using Tensorflow</dt>
      <dd>Memory management, loss function, optimizer (minimizes loss function), gradient descent</dd>
    </dl>
    <dl>
      <dt>Higher level APIs, estimators</dt>
      <dd>TBD </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">Models</a></h3>
  <div class="example">
    <dl>
      <dt>Supervised vs Unsupervised</dt>
      <dd>TBD </dd>
    </dl>
    <dl>
    <dt></dt>
      <dd>Training and Test sets</dd>
    </dl>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/ml.PNG">
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Neural networks</a></h3>
<p>If a machine learning algorithm returns an inaccurate prediction, then an engineer needs to step in and make adjustments. Deep learning structures algorithms in layers to create a neural network that can learn and make intelligent decisions on its own.</p>
  <div class="example">
    <dl>
      <dt>Layers</dt>
      <dd>Consists of inputs, “hidden layers”, and outputs. Hidden layers do not necessarily need to be a blackbox, but modifying them will involve tensor calculations.</dd>
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