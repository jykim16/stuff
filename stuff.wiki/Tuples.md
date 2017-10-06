
## What's a tuple? A triple? What's the difference between a tuple and a set?

A tuple is an ordered series of values, in a **meaningful sequence**.

Tuples are different from simple ordered lists because each index has a specific meaning.

Tuples are different from sets because the latter are unordered and guarantee uniqueness of the values.

### Examples

A coordinate pair is a tuple. The 1st index means "x-coordinate" and the 2nd index means "y-coordinate".

An RGB value is a tuple.  The 1st index means "red", the 2nd index means "green", and the 3rd index means "blue".

### Triples and beyond
Often a tuple is a pair of values, but don't be thrown by the "two" sound in "tuple". You can have a tuple of any length. A "triple" is a tuple with 3 values, as we saw above. An n-tuple is a tuple of n values, so you can talk about "4-tuples", "5-tuples", and so forth.

### Where are they used?

Although JavaScript is the language used at Hack Reactor, and a lovely and versatile and ubiquitous language it is, many HR grads are also interested in Python, since it is also widely used to build server-side programs.

Python has a distinct data type called a tuple. It is often used to return more than one value from a function. Since tuples in Python are immutable, they are also used as dictionary keys. It can be handy to glom together multiple fields of an object as its "primary key" so to speak in this way.

Ruby also has tuples, via a standard library.

JavaScript does not have tuples as such.  However, when you return an array from a function and assign each element to a separate variable, you effectively have returned a tuple, because the order matters and each index has a meaning.

This can be useful in combination with ES6 destructuring.

```
function getCoordinate() {
  return [10, 20];
}
 
let [posX, posY] = getCoordinate();
```