https://twitter.com/Franc0Fernand0/status/1431549574196367367?s=20&t=kObvIjelj9qDiu4mJE-FGg

Range sum queries on arrays are a frequent topic in coding interviews and competitive programming problems.

If the array values are fixed, the most efficient approach to implement these queries is to build a prefix sum array.

Do you want to know more?

A thread 🧵



Given an array of n integers A[0,...,n], a range sum query Q(i,j) is the sum of the element of A between the indices i and j (here i <= j).

The naive way to compute Q(i,j) is to iterate from A[i] to A[j] and sum the elements.

This takes linear time.

We can do better. We can efficiently compute any range sum query by preprocessing the array and constructing a prefix sum array.

Given an array of n integers A[0,...,n], its prefix sum array is an array P[0,...,n] such that P[i] is equal to the sum of the elements between A[0] and A[i].

👇

In other words, each value in the prefix sum array is equal to the sum of the values in the original array up to the corresponding index.

The prefix sum array is built in linear time and requires linear space, but it is extremely useful for computing range sum queries. Given an array of n integers A[0,...,n] and its prefix sum array P[0,...,n], a range sum query can be computed as:

- Q(i,j) = P[j] - P[i-1]

This is easy to verify visually 👇

Let's consider A = [1,6,5,4,8,3,4,2,1,5]

Its prefix sum is P = [1,7,12,16,24,27,31,33,34,39]

Let's compute Q(4,7).

Using the original array we have that:

- Q(4,7) = 8+3+4+2 = 17

Using the prefix sum array we have that:

- P(4,7) = P[7] - P[3] = 33-16 = 17



The same idea generalizes also to higher dimensions.

For example a 2D prefix sum array can be used to calculate the sum of any rectangular subarray in costant time.

Each sum in this array corresponds to a subarray that begins at the upper-left corner of the array.



As an example of application, let's consider a classic #leetcode problem.

Given an array of integers, find the number of subarrays where the sum of all their elements is equal to k. If N is the length of the array, the brute force solution takes O(N^3) time and follow those steps:

- considers every possible subarray in O(N^2)

- compute the sum of each subarray in O(N)

- increment a counter if this sum is equal to k

The brute force solution can be improved to O(N^2) time using the prefix sum:

- consider every possible subarray in O(N^2)

- compute the sum of each subarray in O(1)

- increment a counter if this sum is equal to k

For this specific problem, the solution can be further improved.

If the sum of the elements of a subarray A[i,...,j] is equal to k, in terms of prefix sum array we have that:

- P[j]-P[i-1] = k

but also that

- P[j] = k - P[i-1]

👇

So we can traverse P using the index j and increment our counter every time we meet an element P[j] such that:

- P[j] = k - P[i]

where i < j.

But how do we know if (and how many) elements P[i] have we meet when we are at index j?

👇

We can store all the values P[j] we meet while traversing the array together with the number of their occurrences using an hash table.

Add and retrieve values from the hash tables takes O(1) time, so the time complexity becomes O(N) since we only traverse the array once.
