## Overview

"Idiomatic" coding following the conventions of a given language. It is the most concise, convenient, and common way of accomplishing a task in that language, rather than forcing it to work in a way that you are familiar with in a different language.

## A simple example in JS

Awkward:

```
if (out === "") {
  // blah
}
```

Awkward:

```
if (out === undefined) {
  // blah
}
```

Idiomatic:

```
if (!out) {
  // blah
}
```