## Linked lists (singly-linked)
A linked list can typically only be accessed via its head node. From there you can only traverse from node to node until you reach the node you seek. Thus **access is O(n)**.

Searching for a given value in a linked list similarly requires traversing all the elements until you find that value. Thus **search is O(n)**.

Inserting into a linked list requires re-pointing the previous node (the node before the insertion point) to the inserted node, and pointing the newly-inserted node to the next node. Thus **insertion is O(1)**. 

Deleting from a linked list requires re-pointing the previous node (the node before the deleted node) to the next node (the node after the deleted node). Thus **deletion is O(1)**.

There is no "worst case" to worry about.