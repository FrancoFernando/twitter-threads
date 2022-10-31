The 2 pointers method is a common technique used in coding interviews and programming.

This is how it works: {1/5} ↓

The key idea is to have 2 pointers (i.e. 2 indexes) moving through an array.

Each pointer moves in one direction only, ensuring the method is efficient. 

Let's consider an example where we have an array of n positive integers and a target sum t.

{2/5}

The goal is to find if a subarray whose sum is x exists.

For this problem, the pointers identify a subarray's first and last value. 

On each step, the left pointer moves one position to the right.

{3/5}

The right pointer moves to the right as long as the subarray sum is at most t.

If the sum becomes exactly t, a solution has been found.

The algorithm's time complexity depends on the number of moves of the pointers.

{4/5}

The left pointer runs in O(n) since it moves one position at each step.

The right pointer has no explicit upper bound at each step.

But it moves a total of n times during the whole algorithm since it always moves to the right.

So time complexity is O(n).

{5/5}
