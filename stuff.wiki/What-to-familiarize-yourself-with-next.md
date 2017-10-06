
## What to familiarize yourself with next

During the Prep course, you practiced component / systems thinking in miniature and you made small programs with a small subset of programming tools and techniques. 

As you proceed on the next step toward being a professional programmer, you must begin thinking about components and your work on a larger scale.

This study guide will help you focus on some key topics to become aware of -- **not** to become expert at, there's too much material to take in one pass. Just start building up a mental framework of areas and topics of interest, and you can deepen your knowledge as you go.

I repeat: DO NOT try to absorb every bit of knowledge that's linked out from this doc, you will drive yourself crazy!  Just skim around and get a sense of what topics are out there to absorb over time, begin to set up a learning scaffold for yourself for more-advanced material.

Let's organize the information in terms of what your simple, early programs didn't try to tackle just yet, but you will need to tackle as you expand your scope.

## Your programs ran inside an online editor

Of course, going forward, you will need to construct programs on your local machine.

Also, right now your code is all on one page (file). As soon as you have more than one file, you have to organize it all. 

You should try out and start using one of these editors:

* [vim](https://scotch.io/tutorials/getting-started-with-vim-an-interactive-guide) (command line only)
* [emacs](http://www.jesshamrick.com/2012/09/10/absolute-beginners-guide-to-emacs/) (command line only)
* [Sublime Text](https://www.sublimetext.com/) (graphical interface)
* [Atom](https://atom.io/) (graphical interface)

Of course you can use any other editor you wish, but the above are some common choices to examine.

Note: The command line ones are cool because programmers work entirely with text, so keeping your hands on the keyboard and using key combos to manipulate text is extremely fast. There's a learning curve to picking them up, but just be aware of that as an option.

## Your programs used only a small subset of JavaScript

First review what you know...

* [MDN page - Quick overview of JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)

Then expand out to a couple of other cool things. Don't tackle [all the ES6 goodies](http://es6-features.org/#Constants) yet, it's too much material!

### JS Scope

* [a good overview of scope](https://toddmotto.com/everything-you-wanted-to-know-about-javascript-scope/)

#### closures

* [MDN on closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
* [sexy explanation of closures](http://javascriptissexy.com/understand-javascript-closures-with-ease/)
* [freecodecamp on closures](https://medium.freecodecamp.com/lets-learn-javascript-closures-66feb44f6a44#.29w6gba0a)

#### hoisting

* [an explanation of hoisting](http://www.adequatelygood.com/JavaScript-Scoping-and-Hoisting.html)
* ["be the interpreter" explanation of hoisting](https://john-dugan.com/hoisting-in-javascript/)

#### the `this` keyword

* [illustrated via "method context"](http://helephant.com/2009/11/29/javascript-method-context/)
* [a longer treatment](http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/)

### Prototypes

* [MDN on prototypes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
* ["in plain english"](http://javascriptissexy.com/javascript-prototype-in-plain-detailed-language/)


## Your programs did not explicitly take into account different programming paradigms

Some major programming paradigms:

* Imperative
* Declarative
* Object-oriented
* Functional

Professional programmers are at least broadly aware of all these, and choose the best paradigm for the task at hand. Generally speaking, you should favor functional programming style because it is more maintainable, use objects as much as you need to, and avoid the straight imperative style as much as you can. The declarative style is unavoidable because that is how HTML and SQL work, and you definitely will use those technologies.

### Imperative vs declarative

* [comparison article from FreeCodeCamp](https://medium.freecodecamp.com/imperative-vs-declarative-programming-283e96bf8aea#.894kcj5i1)

### Object-oriented programming
* [MDN page on O-O](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Introduction_to_Object-Oriented_JavaScript)
* [Codecademy O-O review](https://www.codecademy.com/courses/intro-to-object-oriented-programming/0/1)

### Functional programming

Functional programming is a deep topic but for now just think of it as "use higher-order functions wherever I reasonably can".

* [Eloquent JS Chapter 5](http://eloquentjavascript.net/05_higher_order.html)
* [Mostly Adequate Guide to Functional Programming](https://drboolean.gitbooks.io/mostly-adequate-guide/content/ch3.html) -- this whole book goes very deep but this chapter is a good review of what we covered in Prep
* [A practical intro to functional programming](https://maryrosecook.com/blog/post/a-practical-introduction-to-functional-programming) -- this doesn't use JavaScript but is easy to follow along. Just know that a "lambda" is a fancy word for an anonymous function.


## Your programs did not use explicitly use CS fundamentals like data structures

* [Quick overview of various data structures, using JS](https://www.syncano.io/blog/data-structures-in-javascript/)

### stacks and queues

* [stacks and queues in JS](https://code.tutsplus.com/articles/data-structures-with-javascript-stack-and-queue--cms-23348)

### linked lists
* [CS in JS](https://www.nczonline.net/blog/2009/04/13/computer-science-in-javascript-linked-list/)
* [Tuts+](https://code.tutsplus.com/articles/data-structures-with-javascript-singly-linked-list-and-doubly-linked-list--cms-23392)

### sets
* [Math is fun](https://www.mathsisfun.com/sets/sets-introduction.html)
* [MDN on JS native Set object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)

### trees

* [tree tutorial in JS](https://code.tutsplus.com/articles/data-structures-with-javascript-tree--cms-23393)

### hashtables

* [sparknotes summary](http://www.sparknotes.com/cs/searching/hashtables/section1.html)

### associative arrays

* [the fundamental data structure behind JS objects](http://www.i-programmer.info/programming/javascript/1441-javascript-data-structures-the-associative-array.html)

## Your programs did not worry about performance

* [freecodecamp on complexity analysis of algorithms](https://medium.freecodecamp.com/time-is-complex-but-priceless-f0abd015063c#.7giw15rmf)

## Your programs had no code management

#### Git basics
* [Formal intro](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)
* [Casual intro](http://rogerdudler.github.io/git-guide/)

## Your programs were written solo

Programmers collaborate on development via [Github](http://github.com).

### Github basics
* [Hello World tutorial](https://guides.github.com/activities/hello-world/)

## Your programs were only academically code-reviewed 

Professional engineers use more-formal and robust code review tools, the most popular of which is the "pull requests" facility within Github.

* [Github pull requests](https://yangsu.github.io/pull-request-tutorial/)

## Your programs had no user interface

Without a UI, of course real users will not be able to interact with your program. At Hack Reactor, you will be constructing user interfaces primarily in the browser, although you are likely to have opportunities and/or reason to do so for other types of clients as well.

### HTML & CSS
* [Learn to Code HTML & CSS](http://learn.shayhowe.com/html-css/building-your-first-web-page/)

### DOM
* [MDN page on DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
* [DOM Enlightenment](http://domenlightenment.com/#1) - this is pretty deep, just skim to get the flavor of a formal approach to DOM manipulation. 

## Your programs were not long-running

Your programs were not able to take user input over a long period of time. For a web application programmer, that implies setting up a server.

You will need to learn about:

### Node.js

* [beginners guide](http://blog.modulus.io/absolute-beginners-guide-to-nodejs)

### HTTP

* [very high-level video describing web app request/response](https://www.youtube.com/watch?v=RsQ1tFLwldY)
* [HTTP basics](https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177) -- just skim this to get a sense that knowing this protocol is going to be very important for understanding how you get your browser code to interact with your server code.

## Your programs did not store data

You will need to learn about databases...

### SQL (relational databases)

* [khan academy on SQL](https://www.khanacademy.org/computing/computer-programming/sql)

### NoSQL

* [random marketing blurb on NoSQL db's](https://academy.datastax.com/planet-cassandra/what-is-nosql) -- don't worry too much about these right now, but they are in heavy use, and be aware that SQL databases by no means the only game in town.

## Your programs did not do error handling

### Exceptions

* [Eloquent JS Chapter 8](http://eloquentjavascript.net/08_error.html)

## Your programs had homebrew unit tests

Pros use popular frameworks for unit testing. In JavaScript, you can familiarize yourself for starters with:

* [Mocha](https://mochajs.org/) - test running framework
* [Chai](http://chaijs.com/) - assertion library


