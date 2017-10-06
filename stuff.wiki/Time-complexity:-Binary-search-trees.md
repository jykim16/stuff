## Binary search trees (BST)
As the name suggests, searching for a value in a binary search tree is a binary process. Thus **search is O(log n)**.

In a similar vein, from the root node of a BST, you can traverse to any other node in the tree via the "halving at every step" that is the charmingly efficient core characteristic of BST's.  Thus **access in the best case is O(log n)**.

In practical use, however, "access" usually means traversing every node, via in-order, pre-order or post-order traversal. This implies that in practice **access in the common case is often O(n)**.

To insert a node in a BST, you binary-search the tree until you hit the correct leaf node, which as we saw above is O(log n), then add the value as a new child node of that leaf node, which is O(1). Thus **insertion is O(log n)**.

By similar logic, **deletion is O(log n)**.

### Worst case scenarios for BST's

The worst-case scenarios for BST's all involve a completely unbalanced tree, which degenerates into a singly-linked list.  For example, if you just add 1, 2, 3, 4, 5 in that order to a simple (non-self-balancing) BST implementation, then all your nodes will only have a right child.  You then do not get the "halving at every step" characteristic that gives BST's their power.

In this worst-case scenario:

* **access is O(n)**
* **search is O(n)**
* **insertion is O(n)**
* **deletion is O(n)**

... for the same reason.