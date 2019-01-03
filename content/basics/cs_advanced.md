+++
description = "Algorithms, data structures, networks, CLI"
title = "CS Advanced"
draft = false
weight = 200
bref="Computer Science is the theory, experimentation, and engineering that form the basis for the design and use of computers"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Networks</a></h3>
  <div class="example">
    <dl>
      <dt>LAN</dt>
      <dd>A computer network that spans a relatively small area connected via ethernet and wifi.</dd>
    </dl>
    <dl>
      <dt>WAN</dt>
      <dd>A computer network that spans a large area by connecting multiple LANs. The largest WAN in existence is the Internet.</dd>
    </dl>
    <dl>
      <dt>VPN</dt>
      <dd>Extends a private network across a public network, and enables users to send and receive data across shared or public networks as if their computing devices were directly connected to the private network.</dd>
    </dl>
    <dl>
      <dt>IP</dt>
      <dd>A numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. When communicating with devices within the network, a private IP address is used. When communicating with devices outside the network, a public IP address is used. Since all devices within a private network share the same public IP address, port forwarding is used by the router to determine how to route data among devices. <a href="https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing">CIDR</a> is a method for dividing networks into subnetworks.</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">Command line interface (CLI)</a></h3>
  <div class="example">
    <p>A means of interacting with a computer program where the user (or client) issues commands to the program in the form of successive lines of text (command lines). Most users rely upon graphical user interfaces and menu-driven interactions with a mouse. However, many software developers, system administrators and advanced users still rely heavily on command-line interfaces to perform tasks more efficiently, configure their machine, or access programs and program features that are not available through a graphical interface.</p>
    <p>A Unix shell is a command-line interpreter or shell that provides a command line user interface for Unix-like operating systems. Bash is a Unix shell and command language that can be used for executing commands from the CLI. <i> Windows has their own their shell and command language. Install Git Bash on Windows to run these commands.</i></p>
    <img src="/img/basics/cli.png">
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Algorithmic Complexity</a></h3>
  <div class="example">
    <p>Big O notation is the language we use for talking about how long an algorithm takes to run. It's how we compare the efficiency of different approaches to a problem.</p>
    <p>To demonstrate Big O notation, let's use the example of a phone book. We will assume our phone book has businesses (the "Yellow Pages") which have unique names and people (the "White Pages") which may not have unique names. A phone number is assigned to at most one person or business. We will also assume that it takes constant time to flip to a specific page.</p>
    <p>Here are the running times of some operations we might perform on the phone book, from best to worst:</p>
    <dl>
      <dt>O(1) (best case)</dt>
      <dd>Given the page that a business's name is on and the business name, find the phone number.</dd>
    </dl>
    <dl>
      <dt>O(1) (average case)</dt>
      <dd>Given the page that a person's name is on and their name, find the phone number.</dd>
    </dl>
    <dl>
      <dt>O(log n)</dt>
      <dd>Given a person's name, find the phone number by picking a random point about halfway through the part of the book you haven't searched yet, then checking to see whether the person's name is at that point. Then repeat the process about halfway through the part of the book where the person's name lies. (This is a binary search for a person's name.)</dd>
    </dl>
    <dl>
      <dt>O(n)</dt>
      <dd>Find all people whose phone numbers contain the digit "5".</dd>
    </dl>
    <dl>
      <dt>O(n)</dt>
      <dd>Given a phone number, find the person or business with that number.</dd>
    </dl>
    <dl>
      <dt>O(n log n)</dt>
      <dd>There was a mix-up at the printer's office, and our phone book had all its pages inserted in a random order. Fix the ordering so that it's correct by looking at the first name on each page and then putting that page in the appropriate spot in a new, empty phone book.</dd>
    </dl>
    <p>For the below examples, we're now at the printer's office. Phone books are waiting to be mailed to each resident or business, and there's a sticker on each phone book identifying where it should be mailed to. Every person or business gets one phone book.</p>
    <dl>
      <dt>O(n log n)</dt>
      <dd>We want to personalize the phone book, so we're going to find each person or business's name in their designated copy, then circle their name in the book and write a short thank-you note for their patronage.</dd>
    </dl>
    <dl>
      <dt>O(n<sup>2</sup>)</dt>
      <dd>A mistake occurred at the office, and every entry in each of the phone books has an extra "0" at the end of the phone number. Take some white-out and remove each zero.</dd>
    </dl>
    <dl>
      <dt>O(n · n!)</dt>
      <dd>We're ready to load the phonebooks onto the shipping dock. Unfortunately, the robot that was supposed to load the books has gone haywire: it's putting the books onto the truck in a random order! Even worse, it loads all the books onto the truck, then checks to see if they're in the right order, and if not, it unloads them and starts over. (This is the dreaded bogo sort.)</dd>
    </dl>
    <dl>
      <dt>O(n<sup>n</sup>)</dt>
      <dd>You fix the robot so that it's loading things correctly. The next day, one of your co-workers plays a prank on you and wires the loading dock robot to the automated printing systems. Every time the robot goes to load an original book, the factory printer makes a duplicate run of all the phonebooks! Fortunately, the robot's bug-detection systems are sophisticated enough that the robot doesn't try printing even more copies when it encounters a duplicate book for loading, but it still has to load every original and duplicate book that's been printed.</dd>
    </dl>
    <div style="text-align:center">
      <img src="/img/basics/algos.png">
    </div>
    <div style="text-align:center;margin-top:55px;">
      <img src="/img/basics/sorting.png">
    </div>
  </div>
  <div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section4"><a href="#h-Section4">Data Structures</a></h3>
  <div class="example">
    <div style="text-align:center">
      <img src="/img/basics/data_structures.jpg">
    </div>
    <div class="row">
      <div class="col col-6">
          <figure>
    <img alt="Image" src="/img/basics/bst.png" width="85%">
    <figcaption>
      Binary search trees keep their keys in sorted order, so that lookup and other operations can use the principle of binary search. This means that each comparison allows the operations to skip about half of the tree, so that each lookup is much better than the linear time required to find items by key in an (unsorted) array, but slower than the corresponding operations on hash tables.
    </figcaption>
  </figure>
      </div>
      <div class="col col-6">
        <figure>
    <img alt="Image" src="/img/basics/hash.png">
    <figcaption>
      Hash functions are used in hash tables, to quickly locate a data record (e.g., a dictionary definition) given its search key. Specifically, the hash function is used to map the search key to a list; the index gives the place in the hash table where the corresponding record should be stored. Typically, the set of possible keys is larger than the number of different table indices, and so it will map several different keys to the same index which could result in collisions. So then, each slot of a hash table is associated with a set of records, often called a bucket.
    </figcaption>
  </figure>
      </div>
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>