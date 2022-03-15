https://twitter.com/Franc0Fernand0/status/1434106118914125825?s=20&t=kObvIjelj9qDiu4mJE-FGg

Finding out the space and time complexity of your code can help you to develop better programs that run faster.

Some functions are easy to analyze, but when you have recursion might get a little trickier determining their complexity.

Luckily, you can usually apply a rule 👇

The following rules usually applies for the time complexity of a recursive function:

- O(b^h) if the function calls itself b times at each step
- O(h) if the function calls itself only once

where:

- h = maximum depth of the recursion stack

Why? 👇

Some facts:

1️⃣ the execution of a recursive function can be represented using a tree, known as recursion tree, whose nodes represent all the recursive calls.

2️⃣ in a tree, the maximum number of nodes is equal to a constant factor multiplied by the number of leaves.

👇

3️⃣ big O analysis usually ignores constant factors, so we can consider the time complexity of a recursive function as proportional to the leaves of its recursion tree

Now the question is: how many are these leaves? 👇

The branching factor of a tree is the maximum number of child in a node.

So, the maximum number of leaves in a tree is b^h, where b is branching factor of the tree and h its height.

👇

In the case of recursion trees, the branching factor b is the number of times the function calls itself and the height h is the maximum depth of its recursion stack.

The space complexity is instead proportional to the height h of the recursion tree.
