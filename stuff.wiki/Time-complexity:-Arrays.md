## Arrays

Arrays offer random access to their contents through a numeric index.  Therefore **array access is O(1)**.

Searching for a given value requires iterating through the array. So **array search is O(n)**.

If you know that the array is sorted in a way that's amenable to binary search, then you can search the array that way and achieve **in the best case, array search is O(log n)**.

Inserting into an array requires you to shift all elements to the right by 1. If we say that on average that means `n/2` elements need to be shifted, that devolves to **array insert is O(n)*.

Deleting an element from an array requires you to shift all the elements to the left by 1. By similar logic to the above insertion case, **array deletion is O(n)**.

There is no "worst case" to worry about.