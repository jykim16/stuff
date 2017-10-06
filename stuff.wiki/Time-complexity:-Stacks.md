## Stacks
Stacks offer random access to their contents by popping the top element off the stack. You have to do this repeatedly to access an arbitary element somewhere in the stack.  Therefore, **access is O(n)**.

Searching for a given value in the stack requires repeatedly popping elements off the top of the stack until you find the value you seek. So **search is O(n)**.

Inserting into a stack can only happen at the top of the stack, similar to a burly fireman heaving yet another pancake onto a pile at the fire station pancake-breakfast fund-raiser. So **stack insertion is O(1)**.

Deleting from a stack also only happens at the top of the stack, similar to a hungry street urchin snatching a pancake from the top of the pile and scampering away, trailed by the outraged bellows of the town's cadre of heroic firefighters. So **stack deletion is O(1)**.

There is no "worst case" to worry about.