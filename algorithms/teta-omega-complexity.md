Many use Big O notation to measure space and time complexity of algorithms.

But not everyone knows that this notation is part of a family including also:

• Ω (Big Omega)
• ϴ (Big Theta)

https://twitter.com/Franc0Fernand0/status/1519307895720009730?s=20&t=6dU-uE_Tuf7se1a62DaVhA

What's the difference between them ?

// Thread // {1/5} ↓

Let's consider the problem of sorting an array of length n.

A way to solve this problem is using the Insertion Sort algorithm.

Let's restrict the analysis to its worst-case execution.

{2/5}

O-notation provides an approximate definition of less-than or equal-to (<=).

We can say that Insertion Sort worst case complexity is O(n²), because it takes at most a quadratic number of steps.

But we could also say O(n³) because big O establishes only an upper bound.

{3/5}

Ω-notation provides an approximate definition of greater-than or equal-to (>=).

We can say that Insertion Sort worst case complexity is Ω(n²), because it takes at least a quadratic number of steps.

But we could also say Ω(n) because Ω establishes only a lower bound.

{4/5}

ϴ-notation provides an approximate definition of equality (=).

We can say that Insertion Sort worst case complexity is ϴ(n²) because it takes exactly a quadratic number of steps.

ϴ is a stronger notion than O and Ω, defining a tight bound (both upper and lower).

{5/5}
