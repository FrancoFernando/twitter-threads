https://twitter.com/Franc0Fernand0/status/1451481157544128512?s=20&t=kObvIjelj9qDiu4mJE-FGg

Algorithms Explained 🔑

Bubble Sort is one of the simpler sorting algorithms.

It performs multiple iterations over an input array. At each step:

🔸 look at pairs of adjacent elements
🔸 swap their positions if the 1st element is greater than the 2nd

A quick thread.



Here is what happen during the first iteration.

The swapped pairs of adjacent elements are in red.

It is not difficult to implement the algorithm naively.

But you can easily make 2 optimization.



1️⃣ if during an iteration there are no swap, the input array is already sorted and you can stop

2️⃣ at the end of the k-th iteration the n - k - 1 element will be in its final position. So at each iteration you need to look only at the first n - k - 1 elements

Time complexity is O(N^2).

In the worst case you make n-1 iterations, looking at n-1 pairs of adjacent elements.

Space complexity is O(1).

Here a possible implementation of the algorithm in Python. Next tweets in C++ and C#.



Bubble Sort in C++



Bubble Sort in C#

