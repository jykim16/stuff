## Overview

IIFE stands for "immediately-invoked function expression". 

It's basically a self-executing anonymous function.

## Why use it?

### Avoid polluting global scope

In JavaScript until recently, scope was entirely determined by functions. (More recently, `let` and `const` keywords introduce [block-scoping](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Scoping_rules_2).)

To avoid polluting the global scope, you can use an IIFE to encapsulate code in the IIFE's scope.
	
### Aliasing / namespacing

Here's a trivial example of a jQuery plugin, set up in the standard way to protect the `$` alias as well as to keep all plugin references within the `jQuery` namespace:

```
(function ( $ ) {
    $.fn.greenify = function() {
        this.css( "color", "green" );
        return this;
    };
}( jQuery ));
```

The explanation, from [jQuery docs](https://learn.jquery.com/plugins/basic-plugin-creation/):

> The $ variable is very popular among JavaScript libraries, and if you're using another library with jQuery, you will have to make jQuery not use the $ with jQuery.noConflict(). However, this will break our plugin since it is written with the assumption that $ is an alias to the jQuery function. To work well with other plugins, and still use the jQuery $ alias, we need to put all of our code inside of an Immediately Invoked Function Expression, and then pass the function jQuery, and name the parameter $.

### Closures to encapsulate private data

Let's say you wanted to make an "id generator".

Here's one way to do it:

```
const IdGenerator = function() {
  this.id = 0;
}
IdGenerator.prototype.getNextId = function() {
  this.id++;
  return this.id;
}

const generator = new IdGenerator();
console.log(generator.getNextId()); // --> 1
console.log(generator.getNextId()); // --> 2
console.log(generator.getNextId()); // --> 3
console.log(generator.getNextId()); // --> 4
```

However this would allow someone to reach inside and muck with the id:

```
const generator = new IdGenerator();
console.log(generator.getNextId()); // --> 1
console.log(generator.getNextId()); // --> 2
generator.id = 666;
console.log(generator.getNextId()); // --> 667
console.log(generator.getNextId()); // --> 668
```

You could adjust it to prevent that, like this:

```
const IdGenerator = function() {
  let id = 0;

  this.getNextId = function _getNextId() {
    id++;
    return id;    
  }
}
```

But here's a completely different way to accomplish the same thing, without needing to set up a class, using an IIFE:

```
const getNextId = (function() {
  let id = 0;
  return function() {
    id++;
    return id;
  };
})();
```


