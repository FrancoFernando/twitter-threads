https://twitter.com/Franc0Fernand0/status/1453327031412961284?s=20&t=kObvIjelj9qDiu4mJE-FGg

Algorithms Explained 🔑

Selection Sort is a simple sorting algorithm.

It partitions an input array into 2 subarrays: one sorted and one unsorted.

At each step the smallest element of the unsorted subarray is inserted into its proper place in the sorted one.

A quick thread.



Here is what happen at each step:

🔸 the red item is moved from the unsorted to the sorted subarray

🔸 the blue item is swapped with the red one

🔸 the black items are unmoved



Time complexity is O(n^2), where n is the size of the input array.

The algorithm makes n-1 iterations.

At the step k, n-k-1 comparisons are executed to find the index of the smallest item.

Space complexity is O(1).

Here a possible implementation of the algorithm in Python.



Insertion sort in C++ 👇



Insertion sort in C# 👇

