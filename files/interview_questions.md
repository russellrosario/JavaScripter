# ALGORITHMIC COMPLEXITY
* O(1): A function that executes with similar time regardless of size of inputs
* O(log n): Find a result within a sorted context
* O(n): 1 FOR loop performing an operation on every element of an array
* O(n log n): Sorting algorithm that works recursively
* O(n^2): 2 FOR loops (2 dimensional array)
* O(2^n): Fibonacci calculation executes two additional recursive functions until the base case
* O(n!): Brute force password cracking based on password length

# DATA STRUCTURES
* Queue (FIFO) & Stack (LIFO)
* Hash tables
  * A hash table uses a hash function to compute an index into an array of buckets or slots, from which the desired value can be found.
* Linked lists
  * A linear collection of nodes where each node contains data and a reference link to the next node in the sequence
  * ![Linked lists](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Singly-linked-list.svg/408px-Singly-linked-list.svg.png)
* Trees
  * <img src="https://www.w3schools.com/js/pic_htmltree.gif" alt="Tree" width="400"/>
* Binary trees
  * <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/da/Binary_search_tree.svg/300px-Binary_search_tree.svg.png" alt="Binary Tree" width="200"/>

# OTHER COMMON QUESTIONS
* Scope & Closures
  * A scope in JavaScript defines what variables you have access to. There are two kinds of scope – global scope and local scope.
  * Whenever you create a function within another function, you have created a closure. The inner function is the closure. This closure is usually returned so you can use the outer function's variables at a later time.
* This keyword
  * A variable with the value of the object that invokes the function where this is used
  * Can be changed by using .call(), .apply() and .bind()
  * Arrow functions lexically bind their context so this actually refers to the originating context
* Callbacks and asynchronous code
  * Uses event loop for nonblocking async I/O operations using libuv
* Sorting algorithms
  * Bubble - O(n^2) keep walking through the array and sort two items
  * Selection - O(n^2) keep selecting the smallest item of an array and put it into a new sorted array
  * Merge - O(n log n) sort left and right halves recursively and then merge
  * Insertion - O(n^2) take each item of an unsorted array and insert it into the correct location of a newly sorted array
  * Quicksort - O(n log n) Recursively sort by creating pivot elements
  * Binary search - O(log n) compare item to the midpoint of a sorted array
  * Heap - O(n log n) create a tree from the items and then sort left vs right
* Event loop
  * Functions get placed on the call stack
  * Async functions get executed and removed from the call stack and the resulting callback get placed into a callback queue. The event loop brings the callback back to the call stack
* Functional programming
  * The process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects.
* JavaScript classes, and Prototypal inheritance
  * Similar to function constructors
  * uses new keyword
* Hoisting
  * JavaScript's default behavior of moving variable declarations to the top allowing its use before it has been declared
* Project design
  * Start with a mockup
  * List all the features to be implemented (UML)
  * Determine technologies to use (frontend, backend, DevOps)
  * Address obstacles (time, cost, knowledge)
  * How to scale?
* Memoization
  * An optimization technique used primarily to speed up computer programs by storing the results of expensive function calls and returning the cached result when the same inputs occur again

# COMMON REGEX FUNCTIONS
str.test(reg)
```
var str = "The best things in life are free";
var reg = new RegExp("e");
var res = reg.test(str);
```

str.match(reg)
```
var paragraph = 'The quick brown fox jumped over the lazy dog. It barked.';
var reg = /[A-Z]/g;
var found = paragraph.match(reg);
console.log(found); // expected output: Array ["T", "I"]
```

reg.exec(str)
```
var str = "The best things in life are free";
var reg = new RegExp("e");
var res = reg.exec(str);
```

str.replace(str1,str2)
```
var p = 'The quick brown fox jumped over the lazy dog. If the dog reacted, was it really lazy?';
var reg = /dog/gi;
console.log(p.replace(reg, 'ferret')); // expected output: "The quick brown fox jumped over the lazy ferret. If the ferret reacted, was it really lazy?"
```

str.search(reg)
```
let str = "A drop of ink may make a million think";
alert( str.search( /a/i ) ); // 0 (the first position)
```

str.includes('')
```
var sentence = 'The quick brown fox jumped over the lazy dog.';
var word = 'fox';
console.log('The word "' + word + (sentence.includes(word)? '" is' : '" is not') + ' in the sentence'); // expected output: "The word "fox" is in the sentence"
```

str.split('')
```
var str = 'The quick brown fox jumped over the lazy dog.';
var words = str.split(' ');
console.log(words[3]); // expected output: "fox"
```
