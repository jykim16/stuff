## 30-second answer
1. Maintain a queue of tasks.
1. Run a continuous loop that waits synchronously for a task, runs it, and repeats.
1. A task is always "run-to-completion" and cannot be pre-empted by any other message.

## Motivation

The point of the event loop is to organize the entire program-execution paradigm around asynchronicity. This pays big dividends in terms of responsiveness, freeing up the CPU to attend to other matters (aka being "non-blocking").  This was most-useful originally in the context of browser UI's, but now is critical in writing efficient, scalable servers via the Node.js platform. In the latter case, the callbacks that the event loop is managing are related to I/O with resources external to the process -- disk access or network calls to other services. The asynchronicity powered by the JavaScript event loop is what gives Node.js its fabled ability to manage 10k concurrent connections as a chat server, in a single process.

## Slightly more detail
1. JavaScript maintains a queue of messages, which are essentially callbacks.
1. JavaScript also maintains a call stack, which is a stack of frames for nested function calls that have not yet completed evaluating.
1. It runs a `while` loop that waits synchronously for a message, processes the message synchronously, and repeats.
  * The code literally is something like:
  ```
  while (queue.waitForMessage()) {
    queue.processMessage();
  }
  ```
  * Note that `queue.waitForMessage()` will return immediately if the queue already has at least one message in it. Otherwise, it will only return when a message is added to the queue.
1. A message is added to the queue via event listeners that are attached to events, e.g. click handlers on DOM elements. If an event does not have a listener attached, it is simply ignored and no message is created for it.
1. A message is always processed fully, through its entire call stack (e.g. if it calls nested functions). This process cannot be interrupted by any other message: the next message will only be called when the call stack is empty again, i.e. the previous message completed fully.

![Event Loop Diagram](http://blog.carbonfive.com/wp-content/uploads/2013/10/event-loop.png)

### A note on `setTimeout`
When `setTimeout` is used, JavaScript will wait `delay` milliseconds before adding the callback to the queue. At that time, if there are still previous messages in the queue, those will be processed first and our callback may end up being called later than `delay` milliseconds. Thus, `delay` is not a guaranteed exact delay, but a minimum.

This is why setting `setTimeout` on a function with a zero delay will still ensure that the function is called after the current message is finished (and indeed, after everything else that might be in the queue before it).

#### Code:
```
var printStuff = function() {
  console.log('1');
  setTimeout(function() {
    console.log('2');
  }, 0);
  console.log('3');
};
printStuff();
```

#### Console:
```
1
3
2
```

### Useful Resources
* [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop
)
* [The JavaScript Event Loop: Explained](http://blog.carbonfive.com/2013/10/27/the-javascript-event-loop-explained/)
* [Philip Roberts: What the heck is the event loop anyway?](http://2014.jsconf.eu/speakers/philip-roberts-what-the-heck-is-the-event-loop-anyway.html)
* [Video and visual/interactive representation](http://latentflip.com/loupe/)