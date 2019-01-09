+++
description = "Testing levels, Chrome DevTools, Error tracking"
title = "Testing & Debugging"
draft = false
weight = 200
bref="Software testing is an investigation conducted to provide stakeholders with information about the quality of the software product or service under test"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section0"><a href="#h-Section0">Test Driven Development</a></h3>
  <div class="example">
    <dl>
      <dt>TBD</dt>
      <dd>TBD </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Testing Levels</a></h3>
  <div class="example">
    <dl>
      <dt>Unit, function, acceptance</dt>
      <dd>TBD </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">Libraries</a></h3>
  <div class="example">
    <dl>
      <dt>Mocha, Jest, Sinon</dt>
      <dd>TBD </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Chrome DevTools</a></h3>
  <div class="example">
    <dl>
      <dt>TBD</dt>
      <dd>TBD </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section4"><a href="#h-Section4">Error tracking</a></h3>
  <div class="example">
    <dl>
      <dt>Logs, Sentry</dt>
      <dd>TBD </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

### Whenever possible, use TDD

TDD is a _design process_, not a testing process. TDD is a robust way of designing software components ("units") interactively so that their behaviour is specified through unit tests.

How? Why?

#### Test-first cycle

1. Write a simple failing test
2. Make the test pass by writing the minimum amount of code
3. Refactor the code by applying design principles/patterns

During phase 2, don't bother with quality.

#### Consequences of the test-first cycle

+ Writing a test first makes the code design more testable
+ Writing just the amount of code needed to implement the required functionality makes the resulting codebase minimal, thus more maintainable
+ The codebase can be enhanced using refactoring mechanisms, the tests give you confidence that the new code is not modifying the existing functionalities
+ Cleaning the code in each cycle makes the codebase more maintainable, it is much cheaper to change the code frequently and in small increments
+ Fast feedback for the developers, you know that you don't break anything and that you are evolving the system in a good direction
+ Generates confidence to add features, fix bugs, or explore new designs

Note that code written without a test-first approach is often very hard to test!