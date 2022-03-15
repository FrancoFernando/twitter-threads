https://twitter.com/Franc0Fernand0/status/1451830219791339526?s=20&t=kObvIjelj9qDiu4mJE-FGg

Algorithms Explained 🔑

Insertion Sort is a simple sorting algorithm.

It partitions an input array into 2 subarrays: one sorted and one unsorted.

At each step the 1st element of the unsorted subarray is inserted into its proper place in the sorted one.

A quick thread.



Here is what happen at each step:

🔸 the blue cell represents the sorted subarray.

🔸 the red item is moved from the unsorted to the sorted subarray

🔸 the blue items are shifted to the right to make space for the red one

🔸 the black items are unmoved



Time complexity is O(N^2).

The algorithm makes n-1 iterations.

In the worst case at each step all the items in the sorted subarray are moved to make space for the current unsorted one.

Space complexity is O(1).

Here a possible implementation of the algorithm in Python.



Insertion sort in C++ 👇



Insertion sort in C# 👇

