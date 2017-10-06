## Background
- Officially introduced into Javascript with ES6
- Available in popular libraries such as Bluebird
- From [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise): "The Promise object is used for deferred and asynchronous computations. A Promise represents an operation that hasn't completed yet, but is expected in the future."

## How is it used?

- Takes an ‘executor’ callback function
- Executor callback is executed immediately with resolve and reject functions passed in to be executed on some deferred asynchronous action
- Promises have a ‘then’ method to define what to do when the promise is resolved, and a ‘catch’ method to deal with reject cases
- To create a promise:
    - use new Promise constructor
    - pass in callback that takes resolve and reject as arguments
    - execute some asynchronous function whose callback passes errors to the ‘reject' callback or passes the result to ‘resolve'

## Chaining `then` and `catch`
- All `then` and `catch` both return new promises, which allows chaining

- The first `then` call will receive the argument passed into `resolve`. Subsequent `then` calls will receive the return value from the previous `then` or `catch` that was executed.

- Calling `reject` from within the promise will skip to the first `catch` method. However, any subsequent `then` calls will be executed.

- `catch` methods are executed in 2 situations: (1) when `reject` is called inside the promise or (2) an error is `throw`n from within a promise or `then`/`catch` method.

- If a promise is `reject`ed, only the first instance of the `catch` method will be called. Subsequent catches will only execute if additional errors are thrown.

## Promise All
- `Promise.all` can be used to wait for multiple promises to resolve before executing the `then` method. The `then` method will be passed an array of resolved values from the promises. For example, in the below code, the `[1, 2, 3]` will be logged to the console after all three promises have resolved.
- If any promise in the `Promise.all` calls the reject function, then `Promise.all` will execute the `catch` method instead of the `then` method.

```javascript
let array = [];
let a = new Promise((resolve, reject) => {
	setTimeout(() => {
		resolve(1);
	}, 200)
})

let b = new Promise((resolve, reject) => {
	setTimeout(() => {
		resolve(2);
	}, 500)
})

let c = new Promise((resolve, reject) => {
	setTimeout(() => {
		resolve(3);
	}, 100)
})

Promise.all([a, b, c])
	.then((values) => {
		console.log(values); // [1, 2, 3]
	});
```

## Tips

- Promises can be chained via their ‘then’ and ‘catch’ methods

## References
- [Promise (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)