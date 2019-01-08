+++
description = "JavaScript and its quirks"
title = "JavaScript"
draft = false
weight = 100
bref="JavaScript is a high-level, dynamic, weakly typed, prototype-based, and multi-paradigm interpreted programming language"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Why JavaScript?</a></h3>
  <div class="example">
    <p>JavaScript is a powerful language that can do almost any type of programming (functional, object, imperative). It's growth has made it the most popular language used today. Thousands of libraries and frameworks are available to simplify the task of coding. JavaScript can be run on the client or the server, eliminating the need to switch between different languages and making it the perfect web development tool.</p>

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
      <dd>An object containing a "blueprint" for creating many objects of the same "type". Classes contain a constructor function that is invoked when using the <mark>new</mark> keyword. Instances created through a class definition will inherit methods (functions) and properties of the parent class object through the <b>prototype chain</b>. </dd>
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
      <dd><img src="https://www.javascripter.co/img/languages/js.png" width="85%"></dd>
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
      <dd>As soon as the program runs, "this" is defaulted to the global object. As the program executes, "this" will change to the object it belongs to, which might be different each time the function is called. In a browser event, this refers to the element that received the event. There are <mark>call()</mark>, <mark>bind()</mark>, and <mark>apply()</mark> methods to set the value of a function's "this" regardless of how it's called. There are also arrow functions which don't provide their own this binding (it retains the this value of the enclosing lexical context).</dd>
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
      <dt>Floating points</dt>
      <dd>Unlike many other programming languages, JavaScript does not define different types of numbers, like integers, short, long, floating-point etc. JavaScript numbers are always stored as double precision floating point numbers which means that 1/10 in base 2 is a repeating decimal that will be rounded.</dd>
    </dl>
    <dl>
      <dt>ECMAScript versions</dt>
      <dd>A specification to standardize JavaScript with updates to the language every year. As a result, the latest features of JavaScript might not be able to run in older runtime environments. Fortunately, tools like Webpack and Babel can transpile JavaScript. The transpiler converts the latest versions of JavaScript into earlier versions like ES5 that are compatible with almost all runtimes.</dd>
    </dl>
    <dl>
      <dt>Type coercion</dt>
      <dd>The process of converting values from one type to another (such as string to number, object to boolean, and so on). <i>See chart below for examples.</i> Use <mark>===</mark> to check for equality AND type</ins>. Many developers prefer a statically typed language for issues like this. Using <b>TypeScript</b> adds static typing and other useful features before being transcompiled into JavaScript.</dd>
    </dl>
        <img src="https://www.javascripter.co/img/languages/type_coercion.png">
  </div>
  <div style="text-align:right"> <a href="#top">&#8593; Top</a></div>



<h3 class="section-head" id="h-Section6"><a href="#h-Section6">Resources</a></h3>
  <div class="example">
    <dl>
      <dt><a href="/files/arrays/">Array methods</a></dt>
      <dd>All the functions you will ever need to manipulate array data</dd>
    </dl>
    <dl>
      <dt><a href="/files/js_libraries/">JavaScript Libraries</a></dt>
      <dd>Awesome browser-side JavaScript libraries</dd>
    </dl>
    <dl>
      <dt><a href="/files/js_snippets/">JavaScript Snippets</a></dt>
      <dd>A huge collection of useful functions</dd>
    </dl>
    <dl>
      <dt><a href="/files/design_patterns/">Design patterns</a></dt>
      <dd>Design patterns for commonly occuring themes in software engineering</dd>
    </dl>
    <dl>
      <dt><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript">MDN JavaScript docs</a></dt>
      <dd>The best tutorials and references for JavaScript on the web</dd>
    </dl>
    <dl>
      <dt><a href="https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html">TypeScript in 5 minutes</a></dt>
      <dd> Official documentation from TypeScript</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>
