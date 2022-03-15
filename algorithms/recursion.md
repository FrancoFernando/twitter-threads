https://twitter.com/Franc0Fernand0/status/1423932609764134918?s=20&t=kObvIjelj9qDiu4mJE-FGg

Recursion is a powerful technique for defining and implementing algorithms, but it is not so easy to understand for beginners.

If you want to review the basics concepts related to recursive algorithms, you should read his thread 🧵 👇



Recursion is the process of defining a problem in terms of itself.

An example?

Let's consider the problem of counting the number of odd values in an array A of n integers.

👇

The number of odd integers in A is equal to the number of odd integers in the subarray A[0,..,n-1] plus 1 if A[0] is odd.

Then, the number of odd integers in A[1,.., n-1] is equal to the number of odd integers in the subarray A[2,..,n-1] plus 1 if A[1] is odd. So the problem of counting the number of odd values in an array A[0,... n-1] can be defined in terms of counting the number of odd values in an array A[1,...,n-1]. A recursive solution to a problem can always be written as a function taking some input values and calling itself with different input values.

Let's consider again the previous example of counting the number of odd values in an array.

👇

We could define a function that:

- takes as input an index i
- call itself taking as input the index i+1
- add 1 to value returned by the called function, if the element i is even
- return

Recursive functions

Every recursive function requires two main components:

- the base case
- the reduction step

👇

Base case

Compute an output value without making any subsequent recursive call.

This is done for one (or more) input values for which the function is directly evaluated.

In the counting odd example, the base case is when we reach the end of the array and we return 0. Reduction step

Relate the output value of the function at one (or more) input values to the value of the function at one (or more) other input values.

In the example, the number of odd values starting at index i is related to the number of odd values starting at index i+1

Convergence

A fundamental property of recursive functions is that the sequence of input values in the reduction steps must converge to the base case.

In the example above, the value of the index is incremented at each step and always converge to the size of the array. Output

There are three different ways a recursive function can return an output value:

- storing the result in a global variable
- storing the result in a passed variable
- building up the result as it return from the base case.



Understanding recursive code

The best way for visualizing what happen when a recursive function runs is tracking the value of the variables in the recursion tree.

This tree is a diagram of all the recursive calls.

An example? 👇

Fibonacci

The recursive function for computing the nth fibonacci number, related the nth fibonacci number to both the (n-1)th and (n-2)th fibonacci number.

The resulting recursion tree has a branch factor of 2.



Time complexity

Determining the time complexity for recursive functions is hard, but usually this rule applies:

- O(b^h) if the function calls itself b times at each step
- O(h) if the function calls itself only once

where:

- h = maximum depth of the recursion tree

Space complexity

A recursive algorithm works because the computer holds the computation done in every reduction step on the function stack frame.

So, the space complexity is proportional to the number of reduction steps plus any non-constant space used during every step. Tail recursion optimization

For functions performing the recursive call as final statement, there isn't any need to store stack frames before executing the next reduction step.

This optimization reduces space complexity, but it is not supported by all programming languages.
