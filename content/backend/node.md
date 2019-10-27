+++
description = "Node and NPM"
title = "Node"
draft = false
weight = 100
bref="Node.js is an open-source, cross-platform JavaScript run-time environment that executes JavaScript code outside of a browser"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Understanding Node.js</a></h3>
  <div class="example">
    <dl>
      <dt>Single Threaded, Asynchronous</dt>
      <dd>Node.js operates on a single thread event loop, using non-blocking I/O calls, allowing it to support tens of thousands of concurrent connections without incurring the cost of thread context switching. Node.js relies on the libuv library (written in C) which uses a fixed-sized (multiple) thread pool to handle the non-blocking asynchronous I/O operations. </dd><br/>
      <dd>A downside to the single-threaded approach is that Node.js doesn't allow vertical scaling by increasing the number of CPU cores of the machine it is running on without using a cluster module (such as pm2). Additionally, the number of threads in the libuv thread pool can be updated. The operating system will distribute these threads across multiple cores. Typically, the number of threads or forked processes should equal the number of CPU cores.</dd><br/>
      <dt>V8 Engine and Node.js bindings</dt>
      <dd>V8 is a powerful open source Javascript engine provided by Google that compiles JavaScript source code to native machine code instead of interpreting it in real time. The core functionality of Node.js resides in a JavaScript library. The Node.js bindings, written in C++, connect these technologies to each other and to the operating system. These bindings allow the JavaScript to understand more than what the ECMAScript standard specifies the JavaScript should understand.</dd><br/>
      <dt>Event loop</dt>
      <dd>Node.js registers with the operating system so the OS notifies it of connections and issues a callback. Within the Node.js runtime, each connection is a small heap allocation. Traditionally, processes or threads handled each connection. In contrast, Node.js uses an event loop that does not need to be called explicitly. Any function performing I/O must use a callback, and the server automatically enters the event loop at the end of the callback definition. Node.js exits the event loop when there are no further callbacks to be performed. </dd><br/>
      <dt>Process.env</dt>
      <dd>The process.env global variable is injected by the Node at runtime for your application to use and it represents the state of the system environment your application is in when it starts. Secret variables are stored here rather than in accessible code.</dd><br/>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/backend/nodeJS.jpg">
    </div>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>


<h3 class="section-head" id="h-Section2"><a href="#h-Section2">NPM</a></h3>
  <div class="example">
    <dl>
      <dt>Package manager</dt>
      <dd>npm is the pre-installed package manager for the Node.js server platform. It installs Node.js programs from the npm registry, organizing the installation and management of third-party Node.js programs. Packages in the npm registry can range from simple helper libraries such as Lodash to task runners such as Grunt. </dd>
    </dl>
    <dl>
      <dt>NPM Scripts</dt>
      <dd>Npm has a run command that can run scripts defined in the scripts property of a package.json file. It provides additional commands to the CLI, such as <mark>npm run test</mark>. This functionality reduces the need for third-party tooling like Grunt or Gulp. </dd><br/>
      <dd>You can add even more functionality to NPM scripts by installing open source dev dependencies. npm-run-all can run scripts in parallel (usually multiple tasks are run in sequence with &&). onchange will automatically re-run the task by watching for changes in your code.</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Resources</a></h3>
  <div class="example">
    <dl>
      <dt><a href="/files/node_cheatsheet">Cheat sheet</a></dt>
      <dd>Common Node.js commands</dd><br/>
      <dt><a href="/files/node_packages">NPM Packages</a></dt>
      <dd>The best available NPM packages</dd><br/>
      <dt>Tutorials</dt>
      <dd>
[Node.js Handbook](https://medium.freecodecamp.org/the-definitive-node-js-handbook-6912378afc6e) - The definitive Node.js handbook <br/>
[Node best practices](https://github.com/i0natan/nodebestpractices) - The largest Node.JS best practices list <br/>
[Nodeschool](http://nodeschool.io) - Learn Node.js with interactive lessons. <br/>
[The Art of Node](https://github.com/maxogden/art-of-node/#the-art-of-node) - An introduction to Node.js. <br/>
[stream-handbook](https://github.com/substack/stream-handbook) - How to write Node.js programs with streams. <br/>
[module-best-practices](https://github.com/mattdesl/module-best-practices) - Some good practices when writing new npm modules. <br/>
[You Don't Know Node.js](https://github.com/azat-co/you-dont-know-node) - Introduction to Node.js core features and asynchronous JavaScript.<br/>
[The Node Way](http://thenodeway.io) - An entire philosophy of Node.js best practices and guiding principles exists for writing maintainable modules, scalable applications, and  code that is actually pleasant to read.<br/></dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

