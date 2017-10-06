### Static vs Dynamic 

A statically typed language requires you to declare the type explicitly. Such type markers are evaluated at compile time.

E.g., in Java:

```
int num = 3;
num = 'a'; // Type error is thrown at compile time
```

Obviously JavaScript doesn't exhibit this behavior. The type of a given variable can change at runtime. JavaScript is **dynamically typed**. 

Note that in JavaScript's case, when we say "type of a variable", this is a bit misleading because we are actually talking about the type of the **value** that the variable points to. The variable itself can point at, and be re-pointed at, any value. The values themselves are what are tagged as being a Number or a String, etc.

### Strong vs Weak

A strongly typed language will require you to do something sensible with your values.

This won't fly in Python:

```
>>> x = 'a'
>>> x + 3
TypeError: cannot concatenate 'str' and 'int' objects
```

But in the same situation, JavaScript will happily try to do something it considers reasonable:

```
> x='a'
"a"

> x+3
"a3"
```

This tolerant stance when evaluating mixed types makes JavaScript a **weakly typed** language.
