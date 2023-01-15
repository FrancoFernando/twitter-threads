Fast and slow pointers are a great technique to manipulate linked lists.

It comes in very handy in solving interview problems.

Here is how it works: {1/5} ↓

Fast and slow pointers are an extension of the arrays 2 pointers method to linked list.

The idea is to iterate through the list with 2 pointers moving at different speeds.

The pointers are usually called fast and slow.

{2/5}

Let's consider an example where we want to find the node in the middle of a list.

The brute force approach would first find the list's length and then the middle node.

Fast and slow pointers give a more efficient and elegant solution with only one iteration.

{3/5}

On each step, the fast pointer advance by 2 nodes and the slow pointer by 1 node.

This way, the slow pointer reaches the middle node while the fast one reaches the end. 

This is because the slow pointer moves at half the speed.

{4/5}

Of course, this approach has some variants.

For example, the pointers can start at different locations or have different speeds ratio.

Other common problems that can be solved with this method are:

- find if a list has a cycle

- remove duplicates from a sorted list

{5/5}
