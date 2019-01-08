+++
description = "React, React Router, Redux"
title = "React"
draft = false
weight = 300
bref="React is a JavaScript library for building user interfaces. It is maintained by Facebook and a community of individual developers and companies."
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section0"><a href="#h-Section0">Basics</a></h3>
  <div class="example">
    <dl>
      <dt>What makes up React?</dt>
      <dd><b>React DOM</b> - React is rendered in a single root DOM node. Unlike browser DOM elements, React elements are plain objects, and are cheap to create. React DOM efficiently compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.</dd><br/>
      <dd><b>JSX</b> - Instead of artificially separating markup and logic into different files, JSX can be used to create React "elements" that contain both. You can put any valid JavaScript expression inside the curly braces in JSX and it will be compiled back to regular JavaScript using a Babel script.</dd>
    </dl>
    <dl>
      <dt>Components</dt>
      <dd>Components are created using JSX and rendered using React DOM. React has functional and class components. Functional components do not have state and class based components do have state. Components can be composed from other smaller components.</dd>
    </dl>
    <dl>
      <dt>Props</dt>
      <dd>When React sees a user-defined component, any attributes in that tag are passed to the component in an object called “props”. Props are read-only and cannot be modified. Everything between JSX tags will be passed to the child component as <mark>props.children</mark>. <i>Note that there are a few differences in React Attributes.</i> Use <mark>className</mark> instead of class and <mark>htmlFor</mark> instead of for.</dd>
    </dl>
    <dl>
      <dt>State</dt>
      <dd>Similar to props, but it is private to the component and modifiable. It is initialized in the constructor method of the component class. A component may choose to pass its state down as props to its child components.</dd>
    </dl>
    <dl>
      <dt>LifeCycle</dt>
      <dd>Component lifecycle methods are called in the following order when an instance of a component is being created and inserted into the DOM: constructor(), render(), componentDidMount(). <mark>constructor()</mark> is called before the component is mounted and is the only place where you should assign <ins>this.state</ins> directly. Otherwise, use <ins>this.setState()</ins>. <mark>render()</mark> is the only required method in a class component. It should return a React element or nothing at all. <mark>componentDidMount()</mark> is invoked immediately after a component is mounted (inserted into the tree). Initialization that requires DOM nodes and loading data from a remote endpoint should go here. <i>There are also other less commonly used lifecycle methods.</i></dd>
    </dl>
    <dl>
      <dt>Handling Events</dt>
      <dd>With JSX you pass a function as the event handler, rather than a string. See all of React's SyntheticEvents <a href="https://reactjs.org/docs/events.html">here</a>. Use ES6 functions for simplifying the binding of <mark>this</mark>.</dd>
    </dl>
    <dl>
      <dt>Conditional Rendering</dt>
      <dd>You can create distinct components that encapsulate behavior you need. Then, you can render only some of them, depending on the state of your application. You can use an inline if with the <mark>&&</mark> operator or <mark>condition ? true: false</mark> ternary operator. </dd>
    </dl>
    <dl>
      <dt>Lists and keys</dt>
      <dd>Use <mark>map()</mark> to transform arrays into React functional component. Keys help React identify which items have changed, are added, or are removed. Keys should be given to these elements to give them a stable identity. Pass these keys as props to the functional component.</dd>
    </dl>
    <dl>
      <dt>Additional features</dt>
      <dd><b>Refs</b> - provide a way to access DOM nodes or React elements created in the render method.</dd><br/>
      <dd><b>Fragments</b> - A common pattern in React for returning multiple elements. Usually this is done by appending 1 div node containing JSX to the DOM.</dd><br/>
      <dd><b>Higher Order Component (HOC)</b> - a function that takes a component and returns a new component. It is used for reusing logic by wrapping the original component with additional functionality.</dd><br/>
      <dd><b>Type checking</b> - As your app grows, you can catch a lot of bugs with typechecking. You can use JavaScript extensions like Flow or TypeScript or the built-in <mark>propTypes</mark>. </dd>
    </dl>
    <dl>
      <dt>Why I prefer React to Angular</dt>
      <dd><b>JSX > TypeScript</b> - JSX is easy to learn and allows for combining of markup and logic.</dd><br/>
      <dd><b>Virtual DOM > MVC</b> - Unidirectional data flow from parent to child component is easy to understand and predictable as opposed to Angular's two-way binding.</dd><br/>
      <dd><b>Library > framework</b> - React's library is flexible to use many open source packages. Angular's framework comes built-in with many components (forms, router, etc.)and a lot of packages are incompatible with TypeScript.</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Libraries</a></h3>
  <div class="example">
    <dl>
      <dt>React Router</dt>
      <dd>Offers a way to write your code so that it will show certain components of your app only if the route matches what you define. The 3 components you will interact the most when working with React Router are: BrowserRouter, Link, and Route. <mark>BrowserRouter</mark> wraps all your Route components. <mark>Link</mark> is used to generate links to your routes. <mark>Route</mark> is responsible for showing the components they contain.</dd><br/>
      <dd>React Router offers a way to match on URL params using <mark>:</mark> before the param. It also allows for nested routing. For this to work, the component needs to be wrapped in a higher order component from React Router called <mark>withRouter</mark>.</dd>
    </dl>
    <dl>
      <dt>State management</dt>
      <dd><b>Lifting state up</b> - If several components need to reflect the same changing data, the shared state can be lifted to their closest common ancestor. The common ancestor will pass a function down to its child components. The child component will invoke the parent component's function with the common data that needs to be changed. The lifecycle method will fire and the child components will be re-rendered with updated props.</dd>
      <dd><b>Redux</b> - Lifting state can be tedious in a complex app so many developers prefer to use a library called Redux for state management. Provides <mark>&lt;Provider/&gt;</mark> which makes the Redux store available to the rest of the app. It also provides a <mark>connect</mark> function for components to connect to the store via <mark>mapStateToProps</mark> and <mark>mapDispatchToProps</mark>.</dd>
    <div class="row">
      <div class="col col-6">
        <figure>
          <img alt="Image" src="https://www.javascripter.co/img/frontend/redux1.png" width="100%">
        </figure>
      </div>
      <div class="col col-6">
        <figure>
          <img alt="Image" src="https://www.javascripter.co/img/frontend/redux2.png">
        </figure>
      </div>
    </div>
      <dd><b>Context</b> - A new feature of React that provides a way to share values like these between components without having to explicitly pass a prop through every level of the tree. In the parent component, create a context with <mark>React.createContext()</mark> and create a provider that returns the context.Provider. The child component can access the context through <mark>context.Consumer</mark>.</dd>
      <dd><b>Redux vs Context</b> - React Redux uses context internally but it doesn’t expose this in the public API. So you should feel much safer using React Redux because if it changes, the burden of updating the code will be on React Redux and not you. However, with a simple app, it might be easier to implement Context quickly.</dd>
    </dl>
    <dl>
      <dt>Tools</dt>
      <dd><b>Create React App</b> - a toolchain used for rapid development. It includes a package manager (NPM), bundler (webpack), compiler (Babel), boilerplate code, and development environment for quickly writing code to production. Create React App produces a <ins>Single Page Application (SPA)</ins> that loads a single HTML page and dynamically updates that page as the user interacts with the app. Usually, the entire website bundle must be downloaded before anything is displayed (<ins>client side rendering</ins>), but there are ways of <ins>lazy loading</ins> (downloading when needed) for a faster client experience.</dd><br/>
      <dd><b>Gatsby</b> - a <ins>static site generator</ins> that lets you use React components and outputs pre-rendered HTML/CSS. If your application doesn't contain dynamic content, using Gatsby will guarantee the fastest load time.</dd><br/>
      <dd><b>Next.js</b> - a popular and lightweight framework for <ins>server‑rendered</ins> applications built with React. <i>See diagram below for difference between server and client rendering</i></dd><br/>
      <dd><b>React Native</b> - A framework for building native applications using JavaScript. React Native compiles to native app components, which makes it possible for you to build native mobile applications. In React JS, React is the base abstraction of React DOM for the web platform, while with React Native, React is still the base abstraction but of React Native. So the syntax and workflow remain similar, but the components are different.</i></dd>
    </dl>
          <img alt="Image" src="https://www.javascripter.co/img/frontend/rendering.PNG" width="100%">
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>


<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Resources</a></h3>
  <div class="example">
    <dl>
      <dt><a href="https://reactjs.org/docs/getting-started.html">React documentation</a></dt>
    </dl>
    <dl>
      <dt><a href="https://devhints.io/react">React cheatsheet</a></dt>
    </dl>
    <dl>
      <dt><a href="https://github.com/brillout/awesome-react-components">Awesome react components</a></dt>
    </dl>
    <dl>
      <dt><a href="https://redux.js.org/introduction/getting-started">Redux documentation</a></dt>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>
