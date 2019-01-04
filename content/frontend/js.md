+++
description = "JavaScript basics, quirks, CLI"
title = "JavaScript"
draft = false
weight = 300
bref="JavaScript is a high-level, dynamic, weakly typed, prototype-based, and multi-paradigm interpreted programming language"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section0"><a href="#h-Section0">Getting started with the CLI</a></h3>
  <div class="example">
    <p>The Command line interface (CLI) is a means of interacting with a computer program where the user (or client) issues commands to the program in the form of successive lines of text (command lines). Most users rely upon graphical user interfaces and menu-driven interactions with a mouse. However, many software developers, system administrators and advanced users still rely heavily on command-line interfaces to perform tasks more efficiently, configure their machine, or access programs and program features that are not available through a graphical interface.</p>
    <p>A Unix shell is a command-line interpreter or shell that provides a command line user interface for Unix-like operating systems. Bash is a Unix shell and command language that can be used for executing commands from the CLI. <i> Windows has their own their shell and command language. Install Git Bash on Windows to run these commands.</i></p>
    <img src="/img/basics/cli.png">
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Why JavaScript?</a></h3>
  <div class="example">
    <p>JavaScript is a very powerful language that can do almost any type of programming (functional, object, imperative). It's growth has made it the most popular language used today. Thousands of libraries and frameworks are available to simplify the task of coding. JavaScript can be run on the client or the server, eliminating the need to switch between different languages and making it the perfect web development tool.</p>

  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">The basics</a></h3>
  <div class="example">
    <dl>
      <dt>Variable</dt>
      <dd>Containers for storing data values. Data values can be any of the 6 primitive data types or an object.</dd>
    </dl>
    <dl>
      <dt>Primitive data types</dt>
      <dd><b>Boolean</b> - "true" or "false"</dd>
      <dd><b>Null</b> -  the intentional absence of any value</dd>
      <dd><b>Undefined</b> - indicates that a variable has not been assigned a value, or not declared at all</dd>
      <dd><b>Number</b> - integer or float</dd>
      <dd><b>String</b> - a series of characters inside double or single quotes</dd>
      <dd><b>Symbol</b> - this data type is used as the key for an object property when the property is intended to be private, for the internal use of a class or an object type</dd>
    </dl>
    <dl>
      <dt>Object</dt>
      <dd>A <ins>non-primitive</ins> data type containing key-value pairs where the key is a string (also called “property name”), and value can be anything.  Arrays, functions, dates, and errors are all of type object. Copying a variable referencing a primitive data type will pass the value to the new variable. However, because objects are a non-primitive data type, copying a variable yields a reference to the original object (NOT the value).</dd>
    </dl>
    <dl>
      <dt>Array</dt>
      <dd>An object containing an indexed list of values of any data type.</dd>
    </dl>
    <dl>
      <dt>Function</dt>
      <dd>An object containing a block of code designed to perform a particular task. It is executed when invoked with <mark>()</mark>. The function completes with a return statement. If the function has parameters, invoking it will pass an array named arguments to the function. Because functions are objects, they can themselves be passed as arguments to other functions. Passing functions as arguments enables <b>asynchronous</b> programming.</dd>
    </dl>
    <dl>
      <dt>Class</dt>
      <dd>An object containing a "blueprint" for creating many objects of the same "type". Classes contain a constructor function that is invoked when using the <b>new</b> keyword. Instances created through a class definition will inherit methods (functions) and properties of the parent class object through the <b>prototype chain</b>. </dd>
    </dl>
    <dl>
      <dt>Conditionals</dt>
      <dd>JavaScript has an "if/else if/else" statement, a ternary operator, and a switch statement.</dd>
    </dl>
    <dl>
      <dt>Loops</dt>
      <dd>A block of code useful for running the same code over and over again, each time with a different value. Often this is the case when working with arrays or objects. Use a for loop for looping every item in an array. "For/in" loops through the properties of an object. "While" loops through a block of code while a specified condition is true.</dd>
    </dl>
    <dl>
      <dt>Operators</dt>
      <dd><img src="/img/frontend/js1.png" width="85%"></dd>
    </dl>
  </div>
  <div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">The quirks</a></h3>
  <div class="example">
    <dl>
      <dt>"use strict"</dt>
      <dd>JavaScript's strict mode that eliminates some silent errors by changing them to throw errors. For example, an error will be thrown when using undeclared variables.</dd>
    </dl>
    <dl>
      <dt>"this" keyword</dt>
      <dd>As soon as the program runs, "this" is defaulted to the global object. As the program executes, "this" will change to the object it belongs to, which might be different each time the function is called. In a browser event, this refers to the element that received the event. There are call(), bind(), and apply() methods to set the value of a function's "this" regardless of how it's called. There are also arrow functions which don't provide their own this binding (it retains the this value of the enclosing lexical context).</dd>
    </dl>
    <dl>
      <dt>Closures & Scopes</dt>
      <dd>A closure is the combination of a function and the lexical scope within which that function was declared. Variables defined inside a function are not accessible from outside the function. Variables defined outside the function are accessible inside the function.</dd>
    </dl>
    <dl>
      <dt>Hoisting</dt>
      <dd>JavaScript's default behavior of moving declarations to the top. This occurs during the compilation step when the JavaScript engine creates the program's scopes before the interpreter executes the code.</dd>
    </dl>
    <dl>
      <dt>Type coercion</dt>
      <dd>The process of converting value from one type to another (such as string to number, object to boolean, and so on). Use === to check for equality AND type.</dd>
    </dl>
    <dl>
      <dt>Floating points</dt>
      <dd>Unlike many other programming languages, JavaScript does not define different types of numbers, like integers, short, long, floating-point etc. JavaScript numbers are always stored as double precision floating point numbers which means that 1/10 in base 2 is a repeating decimal that will be rounded.</dd>
    </dl>
    <dl>
      <dt>ECMAScript versions</dt>
      <dd>A specification to standardize JavaScript with updates to the language every year. As a result, the latest features of JavaScript might not be able to run in older runtime environments. Fortunately, tools like Webpack and Babel can transpile JavaScript. The transpiler converts the latest versions of JavaScript into earlier versions like ES5 that are compatible with almost all runtimes.</dd>
    </dl>
    <dl>
      <dt>TypeScript</dt>
      <dd>A strict syntactical superset of JavaScript that adds optional static typing to the language. Existing JavaScript programs are also valid TypeScript programs. Many developers prefer a statically typed language due to improved debugging and type inference. In addition, TypeScript extends functionality by providing additional language features and transpiling. </dd>
    </dl>
        <img src="/img/frontend/type_coercion.png">
  </div>
  <div style="text-align:right"> <a href="#top">&#8593; Top</a></div>



<h3 class="section-head" id="h-Section6"><a href="#h-Section6">Additional resources</a></h3>
  <div class="example">
    <dl>
      <dt><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript">MDN JavaScript docs</a></dt>
      <dd>The best tutorials and references for JavaScript on the web</dd>
    </dl>
    <dl>
      <dt><a href="/files/arrays/">Array methods</a></dt>
      <dd>All the functions you will ever need to manipulate array data</dd>
    </dl>
    <dl>
      <dt><a href="/files/snippets/">JavaScript Snippets</a></dt>
      <dd>A huge collection of useful functions</dd>
    </dl>
    <dl>
      <dt><a href="/files/design_patterns/">Design patterns</a></dt>
      <dd>Design patterns for commonly occuring themes in software engineering</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>
