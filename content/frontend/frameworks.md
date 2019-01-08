+++
description = "Bootstrap & jQuery"
title = "Frontend tools"
draft = false
weight = 400
bref="JavaScript frameworks provide tooling to efficiently handle commonly faced problems in client-side development"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Bootstrap</a></h3>
  <div class="example">
  <p>A free and open-source front-end framework for developing websites and web applications. It contains HTML- and CSS-based design templates for typography, forms, buttons, navigation and other interface components, as well as optional JavaScript extensions.</p>
    <dl>
      <dt><a href="https://www.w3schools.com/bootstrap4/bootstrap_ref_all_classes.asp">Classes</a></dt>
      <dd>Bootstrap has styling classes for tables, margins, padding, borders, alignment, color, and much more. Steer clear of type selectors (e.g., input[type="text"]) and extraneous parent classes (e.g., .parent .child) that make styles too specific to easily override.
    </dl>
    <dl>
      <dt><a href="https://getbootstrap.com/docs/4.0/components">Components</a></dt>
      <dd>These components make use of the popper JavaScript files added to the HTML file. Bootstrap comes built-in with the most commmon components such as navbar, forms, and buttons.</dd>
    </dl>
    <dl>
      <dt>Grid system</dt>
      <dd>A mobile-first flexbox grid to build layouts of all shapes and sizes thanks to a twelve column system. Each column of a row contains a col class specifying how many of the 12 columns it can possibly take up (no more than 12 total). These classes can also take a prefix (e.g. <mark>.col-sm-</mark>, <mark>.col-lg-</mark>) specifying which devices they apply to. Media queries are optionally used to specify the breakpoints (in pixels) for these class prefixes.</dd>
    <div style="text-align:center">
        <img alt="Image" src="https://www.javascripter.co/img/frontend/grid.png">
    </div>
    </dl>
    <dl>
      <dt>z-index</dt>
      <dd>For overlapping components, Bootstrap uses a modifiable z-index to determine priority of overlapping.</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">jQuery</a></h3>
  <div class="example">
  <p>A fast, small, and feature-rich JavaScript library. It makes things like HTML document traversal and manipulation, event handling, animation, and Ajax much simpler with an easy-to-use API that works across a multitude of browsers.</p>
    <dl>
      <dt><a href="http://api.jquery.com/category/selectors/">Selectors</a></dt>
      <dd>jQuery accepts the same selectors that apply in CSS. It also provides its own. <dd>
      <dt><a href="http://api.jquery.com/category/traversing/">Traversing</a></dt>
      <dd>Filters for traversing the DOM and selecting elements.<dd>
      <dt><a href="http://api.jquery.com/category/attributes/">Attributes</a></dt>
      <dd>A list of methods that get and set DOM attributes of elements</dd>
      <dt><a href="http://api.jquery.com/category/events/">Events</a></dt>
      <dd>These methods are used to register behaviors to take effect when the user interacts with the browser, and to further manipulate those registered behaviors.</dd>
      <dt><a href="http://api.jquery.com/jquery.ajax/">Ajax requests</a></dt>
      <dd>
<pre><code>$.ajax({
  method: "GET",
  url: "website.com/index.html",
  data: null,
  success: function(){console.log('SUCCESS!')},
  failure: function(){console.log('FAILURE!')}
});
</code></pre>
    <div style="text-align:center">
        <img alt="Image" src="https://www.javascripter.co/img/frontend/ajax.gif">
    </div>
      </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>


<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Other options</a></h3>
  <div class="example">
    <dl>
      <dt>Vanilla JavaScript</dt>
      <dd>Refers to using plain JavaScript without any additional libraries. Usually this means the code you write will be <ins>A LOT</ins> more lightweight and faster to load than the entire jQuery library. For example, AJAX requests can be written using XMLHttpRequest. See <a href="http://youmightnotneedjquery.com">"You might not need jQuery"</a> for vanilla JS alternatives to common jQuery functions. </dd><br/>
      <dd><a href="https://javascript30.com/">30 challenge Vanilla JS Coding Challenge</a> - for learning some really cool browser manipulation techniques without needing any libraries or compilers.</dd>
    </dl>
    <dl>
      <dt>CSS</dt>
      <dd>Some of the more popular alternatives to Bootstrap include <a href="https://materializecss.com/">Materialize</a> and <a href="https://semantic-ui.com/">Semantic UI</a></dd><br/>
      <dd><b>SASS/SCSS</b> - a CSS preprocessor that runs on the server and compiles to CSS code that your browser understands. There are client-side alternatives to SASS that can be compiled in the browser using javascript such as LESS CSS, though it is advisable to compile to CSS for production use.</dd><br/>
      <dd><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout">CSS Grid Layout</a> - Alternative to Bootstrap grid. CSS Grid layout divides a page into major regions by defining the relationship in terms of size, position, and layer, between parts of a control built from HTML primitives. </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>