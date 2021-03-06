https://twitter.com/Franc0Fernand0/status/1492517617965350912?s=20&t=mJqlpOKosO7kLkkPhxx7Ow

Coding interviews are hard.

But 95% of people don't use a proper framework.

A 7-steps framework to ace your next inteview.

// Thread // ๐งตโ

Listen

Listen carefully the problem description trying to catch all the information.

Every piece of information is there for a reason and you need it to get an optimal solution.

An example? If the input array is sorted, this will probably affect the optimal solution. Tips:

โ Take your time to fully understand the problem

โ Rephrase the problem with your own words to enforce your understanding

โ Ask questions to clarify any open point

Example

Create an example representing a concrete instance of the given problem.

This will help to:

- double check your problem understanding
- start actively thinking about a solution

The example given by the interviewer is usually too small and cover only a subcase. Tips:

Try to build an example that is

โ big enough to generalize the given problem

โ complex enough to push your brain finding a solution

โ not including special cases (you'll consider this later)

Brute force

Nobody expect that you find immediately the most efficient algorithm.

The best thing you can do is to start from a brute-force solution, explaining its time and space complexity.

You'll then optimize your algorithm from there. Tips:

โ finding a brute force means having already a working solution; this is already a point in your favour

โ in some cases also coming up with brute force solution can be difficult

โ many optimization towards an optimal algorithm can be done from the brute force

Optimize

The most effective approach is the BUD optimization.

Basically, you look for parts that can be removed from the brute force solution like:

๐ผ Bottlenecks slowing down its runtime

๐ท Unnecessary operations that could be avoided

๐ Duplicated operations

Common techniques:

โ use time-space tradeoffs: can additional space speed up your algorithm?

โ brainstorming patterns: is there any data structure that can simplify your algorithm? Or any algorithm technique you can apply (D&C, DP, mapping problem to a graph)

โ solve manually an instance of the problem: can you reverse engineering a better solution?

โ try to use recursion, solving a base case of the problem and building up from there

โ leverage information not used in the brute force algorithm

Walk through

Go through the algorithm and make clear what you are gonna write:

- which data structures you'll use
- where they change

The goal is to have a picture of your code before starting to write it.

You don't need to write many lines and rushing don't help. Coding

You don't need only to write correct code but also a good code:

- modular
- with good variable names

Modularize your code in bottom up way:
- first write a method with high level APIs that solve the problem
- then implement the APIs filling the details

Testing

First analyze and check your code line by line, like during a code review.

Then test your code considering both normal and edge cases (i.e. negative, null, max, min, ...)

If you find a bug, think deeply why it happened and explain this before fixing it

Tips:

โ Double check every math operation like
- additions/subtractions
- increments/decrements

โ Start with small size test cases and go for big only if you have time

โ Test what your code is doing and not what your algorithm is supposed to do
