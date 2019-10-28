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
    <dd>It is very hard to define a human mind with the mathematical rigor of a Turing machine (a programmable algorithm). Although we still do not have a working model of a mouse brain, we do have hardware capable of simulating it. A mouse has around 4 million neurons in the cerebral cortex. A human being has 80-120 billion neurons. Thus, you can imagine how much more research will need to be conducted in order to get a working model of a human mind.

Is there any set of rules that can define the entire scope of human expression? You could argue that we only need to do top-down approach and do not need to understand individual workings of every neuron. In that case you might study some non-monotonic logic, abductive reasoning, decision theory, etc. When new theories come, more exceptions and paradoxes occur. Alternatively, how could any simple logic encompass the evolving meaning that humans attribute to words and abstract ideas?

Although in it's early stages, machine learning attempts to solve this dilemma. By enriching a computer with the ability to improve its output through positive and negative feedback loops, it takes another step closer towards true artificial intelligence. But for now these models are merely Pavlovian conditioning on a singularly focused skill set (in this case natural language). <a href="https://en.wikipedia.org/wiki/G_factor_(psychometrics)">General intelligence</a> displayed by humans is a much broader test of intelligence - one that summarizes positive correlations among different cognitive tasks, reflecting the fact that an individual's performance on one type of cognitive task tends to be comparable to that person's performance on other kinds of cognitive tasks.

Douglas Hofstadter, in his books Gödel, Escher, Bach and I Am a Strange Loop, cites <a href="http://en.wikipedia.org/wiki/G%C3%B6del%27s_incompleteness_theorems#Minds_and_machines">Gödel's theorems</a> as an example of what he calls a strange loop, a hierarchical, self-referential structure existing within an axiomatic formal system. He argues that this is the same kind of structure which gives rise to consciousness, the sense of "I", in the human mind. While the self-reference in Gödel's theorem comes from the Gödel sentence asserting its own unprovability (ie This sentence is false.), the self-reference in the human mind comes from the way in which the brain abstracts and categorises stimuli into "symbols", or groups of neurons which respond to concepts, in what is effectively also a formal system, eventually giving rise to symbols modelling the concept of the very entity doing the perception. Hofstadter argues that a strange loop in a sufficiently complex formal system can give rise to a "downward" or "upside-down" causality, a situation in which the normal hierarchy of cause-and-effect is flipped upside-down. In the case of Gödel's theorem, this manifests, in short, as the following:

    "Merely from knowing the formula's meaning, one can infer its truth or falsity without any effort to derive it in the old-fashioned way, which requires one to trudge methodically "upwards" from the axioms. This is not just peculiar; it is astonishing. Normally, one cannot merely look at what a mathematical conjecture says and simply appeal to the content of that statement on its own to deduce whether the statement is true or false."
    
For example, calculating Pi for a human would yield π, whereas a computer would only stop calculating after it has run out of memory and crashed. According to Godel's incompleteness theorem, a computer cannot escape the inherent limitations of a formal axiomatic ruleset. In the case of the mind, a far more complex formal system, this "downward causality" manifests, in Hofstadter's view, as the ineffable human instinct that the causality of our minds lies on the high level of desires, concepts, personalities, thoughts and ideas, rather than on the low level of interactions between neurons or even fundamental particles, even though according to physics the latter seems to possess the causal power.

    "There is thus a curious upside-downness to our normal human way of perceiving the world: we are built to perceive “big stuff” rather than “small stuff”, even though the domain of the tiny seems to be where the actual motors driving reality reside."

Thus, cognition is a function of how one's own brain categorizes stimuli into a formal system. The presence of free will becomes apparent if these higher level abstractions disagree with the underlying stimuli which gave rise to it.

    Looked at this way, Gödel's proof suggests – though by no means does it prove! – that there could be some high-level way of viewing the mind/brain, involving concepts which do not appear on lower levels, and that this level might have explanatory power that does not exist – not even in principle – on lower levels. It would mean that some facts could be explained on the high level quite easily, but not on lower levels at all. No matter how long and cumbersome a low-level statement were made, it would not explain the phenomena in question.
    
    What might such high-level concepts be? It has been proposed for eons, by various holistically or "soulistically" inclined scientists and humanists that consciousness is a phenomenon that escapes explanation in terms of brain components; so here is a candidate at least. There is also the ever-puzzling notion of free will. So perhaps these qualities could be "emergent" in the sense of requiring explanations which cannot be furnished by the physiology alone. 



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
      <img alt="Image" src="https://www.javascripter.org/img/latest/learning.png">
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
      <img alt="Image" src="https://www.javascripter.org/img/latest/tensor.jpg" width="50%">
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
      <img alt="Image" src="https://www.javascripter.org/img/latest/ml_map.png">
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
      <img alt="Image" src="https://www.javascripter.org/img/latest/activation.png">
    </div>
      <br/>
      <dt>Backpropagation</dt>
      <dd>Shorthand for "the backward propagation of errors," since an error is computed at the output and distributed backwards throughout the network’s layers in order for it to learn from mistakes. Error is calculated and then a <ins>gradient descent</ins> optimization algorithm (a differential equation) is used to determine the direction of steepest decline. In order to avoid local minimas, the learning rate should be gradually adjusted higher.</dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/latest/gradient_descent.png" width="50%">
      <figcaption>
Gradient Descent
      </figcaption>
    </div>
    <dt>Neural network analogy</dt>
      <dd><b>Input layer</b> = Eyes</dd>
      <dd><b>Hidden layer</b> = Brain</dd>
        <div style="margin-left:20px">
        <dd>Activation function = Neurons passing signals to other neurons in the brain</dd>
        </div>
      <dd><b>Output layer</b> = Consciousness (how the brain perceived the stimuli from the eyes)</dd>
        <div style="margin-left:20px">
      <dd>Optimization function = Learning by updating the weights/biases based on the accuracy of previous outputs</dd>
        </div>



</dd>
    </dl>
    <dl>
      <dt>CNN</dt>
      <dd>CNNs have applications in image and video recognition, recommender systems, image classification, medical image analysis, and natural language processing. The input features are taken in batch wise like a filter. This will help the network to remember the images in parts and can compute operations like converting from RGB to grayscale. The changes in the pixel value will help detecting the edges. </dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/latest/cnn.gif">
    </div>
      <dt>RNN</dt>
      <dd>RNNs are applicable to tasks such as unsegmented, connected handwriting recognition or speech recognition. A class of artificial neural network where connections between nodes form a directed graph along a sequence. This allows it to exhibit temporal dynamic behavior for a time sequence. Unlike feedforward neural networks (connections between the nodes do not form a cycle), RNNs can use their internal state (memory) to process sequences of inputs. </dd>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/latest/rnn.png">
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
      <img alt="Image" src="https://www.javascripter.org/img/latest/nn_list.png">
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