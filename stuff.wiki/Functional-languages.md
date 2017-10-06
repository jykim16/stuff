## Overview

> Functional programming is a programming paradigm—a style of building the structure and elements of computer programs—that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.

A functional programming paradigm emphasizes construction programs from **functions**, rather than objects (object-oriented paradigm) or lists of instructions (imperative paradigm).

It's based on the mathematical idea of functions.
 
## Review: What's a mathematical function?

A mathematical function maps one set of values to another set of values (a "domain" to a "range").

For this function...
<table>
  <tr><td><strong>f(x) = x<sup>2</sup></strong></td></tr>
</table>
 
... the mapping, of course, looks like this:
<table>
  <tr><td>1</td><td>1</td></tr>
  <tr><td>2</td><td>4</td></tr>
  <tr><td>3</td><td>9</td></tr>
  <tr><td>4</td><td>16</td></tr>
</table>

Here are some important characteristics to note about mathematical functions that make them useful to consider when writing programming functions.

### Mathematical functions are RELIABLE

Given some INPUT, a valid mathematical function will only map to one OUTPUT. 

No matter how many times you supply that input, a given function will keep producing the same output. 

That makes the function reliable and easy to reason about.

### Mathematical functions are SELF-CONTAINED

Math functions only accept INPUT.

There is no concept of GLOBAL STATE. They do not refer to values other than the input.

This aspect of being self-contained means that they are tidy, predictable black boxes. A change in some value outside of the function will not have an impact on the working of the function.

### Mathematical functions have no SIDE EFFECTS

Math functions only evaluate to their OUTPUT.

Again there is no concept of GLOBAL STATE. They do not affect values outside themselves.

This aspect of having no side effects means that they are tidy, predictable black boxes  The workings of the function will not randomly impact values outside the function.

### Mathematical functions DO ONE THING

Because math functions are self-contained and have no side effects, they can be understood as doing only one thing. They map INPUT to OUTPUT in some predetermined, completely reliable way.  The nature and purpose of that mapping might be quite complex, but the function only performs that mapping. 

### How this applies to programming

The features described above regarding mathematical functions are very useful in the programming world. 

Composing a system from programming functions that are written to behave similarly to mathematical functions means it is a lot easier to reason about that system.

* There will be fewer bugs.
* It will be easier to debug the problems that do arise.
* It will be easier to understand and explain the system to others.
* It will be easier to safely extend it with new functionality.

### This is true even in small programs

Bugs, confusion, and difficulty of extension all happen even in small programs.

Decomposing your problem solution into a system of small, well-named, single-purpose functions with no side effects will reap benefits even at a small scale.

## So, is JavaScript "functional"?

JavaScript is a "multi-paradigm" language. It supports the object-oriented paradigm (albeit in an unusual prototypal-inheritance style) and it of course supports imperative programming. 

It definitely allows you to program in a functional style as well.

* JavaScript supports passing functions as arguments to other functions. 
* JavaScript also supports lambda functions (a two-dollar word for an anonymous function).
     * Lambdas are important because they are a key construct supporting higher-order functions, i.e., functions that can create other functions.
* JavaScript supports higher-order functions.
* JavaScript supports closures (lambda expressions bound to the current state)

That's pretty good stuff for putting functions at the heart of your system!

## It's not completely cut-and-dried...

HOWEVER, here are some things that more "pure" functional languages support that JavaScript does _not_ support:

* first-class, deep support for [immutability](https://wiki.haskell.org/Functional_programming#Immutable_data)
* first-class support for partial application (you can achieve it but it's [not as easy as in Haskell](http://blog.carbonfive.com/2012/09/09/partial-function-application-in-haskell/), for example)
* [algebraic data types](https://wiki.haskell.org/Algebraic_data_type)
* [pattern matching](https://www.haskell.org/tutorial/patterns.html)

## The short answer is...

Yes, JavaScript supports the functional paradigm.









