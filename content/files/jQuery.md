+++
description = "Simple DOM manipulation with jQuery"
title = "jQuery"
date = "2017-04-10T16:43:08+01:00"
draft = false
weight = 200
bref="jQuery is a cross-platform JavaScript library designed to simplify the client-side scripting of HTML"
toc = true
script = 'animation'
+++

# jQuery Cheat Sheet

## Learning Objectives

- Use jQuery to:
  - select elements from the DOM
  - get & modify elements/content in the DOM
  - add elements to the DOM
  - remove elements from the DOM
  - respond to events on the DOM
  - loop through jQuery objects using the `each()` method

## Setup

Create 2 files we'll need:

```bash
$ touch index.html
$ touch script.js
```

in `index.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Document</title>
    <script src="https://code.jquery.com/jquery-2.1.4.js"></script>
    <script src="script.js"></script>
  </head>
  <body>
    <h1>If you can see this in your browser, your Javascript/jQuery is not working!</h1>
  </body>
</html>
```

In `script.js`:

```js
$(document).ready(function() {
  $("body").html("If this wasn't in document.ready, it wouldn't work.");
  for (var i = 0; i < 10; i++) {
    $("body").append("<div class='awesome'>What a great div!</div>");
  }
});
```

## Selecting elements

- `$()`

  - will return all the elements that match the selector given as a jQuery collection
  - the selector can be any valid CSS selector

  ```javascript
  $("div .pizza");
  // will select and return all divs with the class of pizza
  ```

## Modify content

- `.html()`

  - get or set the HTML contents
    - get: no argument, know that it returns the innerHTML of the first jQuery object

  ```javascript
  $(".awesome").html();
  // returns the innerHTML of the first element in the jQuery object
  ```

  - set: one argument that you want the html content to be

  ```javascript
  $(".awesome").html("this is awesome!");
  // returns the innerHTML of the of all elements in the jQuery object to be "this is awesome!"
  ```

- `.text()`
  - get or set the text contained, it will strip the HTML elements
  - same as `.html()` only it returns the text of all jQuery objects selected for the getter portion

Add an input tag to the `index.html`:

```html
<input type="text" class="search" placeholder="some text here ....">
```

- `.css()`

  - acts as both a getter and setter
    - setter: requires 2 arguments(key/value pair), or an object(with multiple key/value pairs)
    - getter: requires 1 argument to get the value of the attribute from the jQuery object

- `.val()`
  - setter: pass in an argument
  - getter: pass in no argument

> We need to be able to get information from users. Input tags are a great way to do that. But more importantly we need to be able to access those values so that our JS can act on it. Think about auto complete on search forms. As we type something into google, it starts giving us options. For every key stroke we make, the callback that is fired is probably using some form of `.val()`. This will also be extremely important moving forward in week 7 with AJAX.

## Adding content

- `.append()`

  - the selector expression preceding the method is the container into which the content(argument) is inserted as the last child

  ```javascript
  $(".awesome").append("<div>this div is appended</div>");
  // this would add the div as the last child in it to all elements with class awesome
  ```

- `.appendTo()`

  - the content precedes the method, either as a selector expression or as markup created on the fly, and it is inserted into the target container(argument) as the last element

  ```javascript
  $("<div>this div is appended</div>").appendTo($(".awesome"));
  // same thing as above
  ```

- `.prepend()`

  - same as append but inserts the specified content(argument) as the first child

  ```javascript
  $(".awesome").prepend("<div>this div is prepended</div>");
  // this would add the div as the first child in it to all elements with class awesome
  ```

- `.prependTo()`

  - same as appendto but the content precedes the method call is inserted as the first child of the target container(argument)

  ```javascript
  $("<div>this div is prepended</div>").prependTo($(".awesome"));
  // same thing as above
  ```

  > Think about how facebook statuses work. When we add a new status, does it go to the bottom of the list? or is it right at the top? Maybe they're using a prepend here ...

## Removing content

- `.remove()`

  - removes the jquery object it is called on, as well as bound events and everything inside it

  ```javascript
  $(".awesome").remove();
  ```

- `.empty()`

  - removes all the child elements of the jquery object it is called on

  ```javascript
  $(".awesome").empty();
  ```

  > Note: when we call the above code, we'll actually be emptying all content from any element with the class of 'awesome'

## Responding to events

- `.on()`

  - a way to create event listeners
  - takes two arguments normally
    - first argument is the event(lots of them)
    - second argument is the callback

  ```javascript
  $(".awesome").on("click", function() {
    console.log($(this));
  });
  ```

> What is `$(this)` here? Refers to the jquery object you called `.on` on, as long as you're in the scope of the `.on` function

### Other

- `.hide()`

  - changes elements style to have `display:none`

  ```javascript
  $(".awesome").hide();
  // returns the innerHTML of the first element in the jQuery object
  ```

- `.show()`

  - changes a `display:none` to `display:block` or whatever it initially was

  ```javascript
  $(".awesome").show();
  // returns the innerHTML of the first element in the jQuery object
  ```

- `.addClass()`

  - does not replace existing classes
  - pass in argument of 1 string to add 1 or more classes

  ```javascript
  $(".awesome").addClass("add three classes");
  // adds the classes add, three and classes to all elements in the jQuery object returned
  ```

- `.removeClass()`

  - pass in argument of 1 string remove 1 or more classes

  ```javascript
  $(".awesome").removeClass("add three classes");
  // removes the classes add, three and classes to all elements in the jQuery object selected
  ```

- `.children()`

  - returns a jQuery object that contains all the child elements of the jQuery object it is called on.

  ```javascript
  $(".awesome").children();
  ```

* `.each()`

  - loops through collections of jquery objects

  ```javascript
  $(".awesome").each(function(index) {
    $(this).html(
      "this html element has the index of ()" + index + ") in the each function"
    );
  });
  ```

> note what the context of `$(this)` is. This refers to each of the elements being looped through.

> This also is actually the second time in this lesson a jquery function requires a callback, can you think of the other?
