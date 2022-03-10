You don't need to be a math expert for DSA.

But some basics are important, like logarithms.

Would you matter if an algorithm takes 1 second instead of 1 day?

Here's how logarithms make this possible.

// THREAD // 🧵↓

Definition

The logarithm is defined by the following equations:

logₖ(x) = y if and only if kʸ = x

where k is the base.

Since the default base in programming is 2, let's consider k=2. Some examples

- log(4) = 2 since 2² = 4
- log(8) = 3 since 2³ = 8
- log(32) = 5 since 2⁵ = 32
- log(1024) = 10 since 2¹⁰= 1024
- .....
- log(4294967296) = 32

What's the take away ?

When y increases by one, x doubles.

As a consequence, when x gets big (i.e. 4 billion) y remains relatively small (i.e 32). Why this is relevant for DSA ?

Each algorithm performs a certain number of basic operations.

For example:

- increase a pointer
- adding two numbers
- accessing an element in an array

are all basic operations. If an algorithm runs in linear time, the number of performed basic operations increases linearly with its input.

An example ?

Traversing an array of 8 numbers involves 8 operations.

Traversing an array of 64 numbers involves 64 operations. If an algorithm runs in logarithmic time, the number of performed operations increases logarithmically with its input.

An example ?

Repeatedly splitting an array of 8 numbers in half and discarding half takes 3 operations.

If the array has 64 numbers, it takes 6 operations. What does it means in practice ?

Let's suppose that one basic operation takes 1 nanosecond to perform and that the size of your input is 1 billion.

A O(N) algorithm takes 1 billion nanoseconds to perform.

A O(logN) algorithm takes ~30 nanoseconds to perform. The first algorithm takes ~1 day to complete, while the second one completes in a heartbeat.

This is why understanding the logarithm function is crucial for algorithms and data structures.
