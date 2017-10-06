# What is the average and worst-case time complexity of access, search, insertion, and deletion for common data structures?

### A note about "access" wrt data structures
First, note that when we talk about "access" in this context, we are talking about "random access". I.e., if you have a target **element** (not a target value) in mind, does the data structure in question afford you the traversal mechanism required to reach that element?

### A note about "search" wrt data structures
When we talk about "search", we are talking about searching for a target **value** within the data structure. You can achieve this either via:

1. The aforementioned random-access traversal of the data structure's elements. In this,  more common style of search, you inspect the value of each element to determine if you have a hit and possibly to determine which element to fetch next (if you have any choice except linear access).
1. Some search mechanism that is offered explicitly as an interface into  this data structure.

## Common data structures

* [[Arrays|Time-complexity:-Arrays]]
* [[Queues|Time-complexity:-Queues]]
* [[Stacks|Time-complexity:-Stacks]]
* [[Linked lists|Time-complexity:-linked-lists]]
* [[Binary search trees|Time-complexity:-Binary-search-trees]]
