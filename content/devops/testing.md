+++
description = "TDD, Chrome DevTools, error tracking"
title = "Testing & Debugging"
draft = false
weight = 200
bref="Software testing is an investigation conducted to provide stakeholders with information about the quality of the software product or service under test. Debugging is the process of finding and resolving defects or problems within a computer program that prevent correct operation of computer software or a system"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Test Driven Development</a></h3>
<div class="example">

#### Whenever possible, use TDD

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
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">Testing</a></h3>
  <div class="example">
    <dl>
      <dt>Unit testing</dt>
      <dd>Individual units/components of a software are tested. A unit is the smallest testable part of any software. It usually has one or a few inputs and usually a single output. </dd>
      <dt>Integration testing</dt>
      <dd>Individual software modules are combined and tested as a group.  </dd>
      <dt>System testing</dt>
      <dd>A complete and integrated software is tested for compliance with the specified requirements. </dd>
      <dt>Acceptance testing</dt>
      <dd>A system is tested for acceptability and ready for delivery. </dd><br/>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/devops/testing.svg">
    </div>
    <figcaption>
    The V-model of software development identifies testing tasks for each stage of development.
    </figcaption><br/>
      <dt><a href="/files/testing_articles/">A curated list of articles related to JavaScript testing</a></dt>
      <dd>Going over from everything from testing libraries, best practices, tips & tricks, and more. </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>


<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Debugging</a></h3>
  <div class="example">
    <dl>
      <dt>Types of errors</dt>
      <dd>
      <ol>
      <li><b>Syntax or interpretation errors</b> - These include mismatched or missing quotes, parentheses and braces, incorrect case, spelling mistakes, illegal characters, and more. These erros can usually be caught using linters like <ins>ESlint</ins> or <ins>JSLint</ins>. Linters analyze your code before it is executed and point out syntax and other common errors.</li>
      <li><b>Runtime exceptions</b> - These are the errors that occur when your JavaScript code executes. Such errors can be triggered by referring to an undefined variable, dividing by zero, by a failed “assert” statement, or by using a “throw” statement in your (or a JavaScript library’s) code to manually specify that an exception has occurred. When a runtime exception occurs, any JavaScript code after that line of code is not executed so they can leave your web page or application in an unexpected state. You can catch and handle runtime exceptions by wrapping the code that fails with a <mark>try {code}</mark> <mark>catch(exception) {}</mark> block.</li>
      <li><b>Incorrect logic</b> - does not show any errors but causes your code to not do what you intend it to. Debugging such errors requires some practice using debugging tools that your browser provides.</li>
      </ol></dd>
      <dt>Chrome DevTools</dt>
      <dd>
      <ul>
      <li><b>Console</b> - Use <mark>console.log()</mark> to dump statements and other useful information like stack variables. Use <mark>console.assert()</mark> to ensure that certain conditions or assumptions are being met in your code. This also dumps the execution call stack and continues execution after the assert.</li>
      <li><b>Debugger</b> - To specify a breakpoint, click on its line number in your code editor or in the Sources panel in <ins>Chrome DevTools</ins>. This will cause the debugger to pause at that line and allow you to inspect variables, the call stack, and evaluate expressions. With the debugger you can continue execution by stepping over the code line-by-line. You can set <ins>watches</ins> for variables and see how they change as you step over the code line by line. DevTools also has <ins>conditional breakpoints</ins> where you can specify the condition when the debugger stops execution.</li>
      <li><b>Working with APIs</b> - The Networks panel in DevTools shows you, for each network request, the “method” (e.g. GET, POST), the HTTP status code (e.g. 200, 403), the MIMEtype (e.g. application/json), the content’s size and whether the network request was fulfilled from the browser’s cache.</li>
      <li><b>Tips</b> - To ensure that your web page is using the latest version of your code, disable the browser cache in the DevTools settings. Also, when inspecting JavaScript objects, remember to use <mark>console.log(JSON.parse(JSON.stringify(obj)));</mark>.</li>
      <li><a href="https://developers.google.com/web/tools/chrome-devtools/">Official Documentation</a></li>
      </ul>
      </dd>
      <dt>Server-side debugging</dt>
      <dd>Logs - cloudwatch</dd>
      <dd>Instance health check</dd>
      <dd>Sentry.io</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>
