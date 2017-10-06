## Queues
Queues offer random access to their contents by shifting the first element off the front of the queue. You have to do this repeatedly to access an arbitary element somewhere in the queue.  Therefore, **access is O(n)**.

Searching for a given value in the queue requires iterating until you find it. So **search is O(n)**.

Inserting into a queue, by definition, can only happen at the back of the queue, similar to someone getting in line for a delicious Double-Double burger at In 'n Out. Assuming an efficient queue implementation, **queue insertion is O(1)**.

Deleting from a queue happens at the front of the queue. Assuming an efficient queue implementation, **queue deletion is O(1)**.

There is no "worst case" to worry about (as long as you don't have a cruddy implementation, see below).

### A note about efficient queue implementation

An inefficient queue implementation would be a naively-manipulated array, wherein all elements are shifted to accommodate an operation at one end of the array. This would be O(n) for one of the operations (enqueue/dequeue).

To achieve O(1) performance, you can implement a queue as either:

* a doubly-linked list, which naturally allows you to manipulate each end as a single operation.
* a "circular array", where you keep track of pointers that tells you where the front and back of the queue reside. The "front" and "back" can float around the array arbitrarily.
