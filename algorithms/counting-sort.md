https://twitter.com/Franc0Fernand0/status/1441390473965236229?s=20&t=kObvIjelj9qDiu4mJE-FGg

🔥 Step by Step guide: Counting Sort 🔥

Comparison-based algorithms have a time complexity of O(nlogn) to sort an array of size n, but there are algorithms capable to sort in O(n) under some conditions.

One is counting sort

How it works and when you can apply it?

A thread.



Prerequisite

Counting sort is a linear time algorithm, but it requires a precondition to be applied.

Each of the n input elements shall be an integer in a finite range or shall have an integer key in that range.

Let's assume for now that the range is [0,k]. The Idea

The basic idea is that the number of times each key occurs in the input array (e.g. its frequency) can be used to determine the position of the elements in the sorted output array.

How? 👇

Let's suppose that there is an element with key equal to c, with c <= k.

If we know that the input array contains m elements with key < c, the index of that element in the sorted output array is clearly equal to m. An example can help to understand better.

Input = [1,1,2,4,3,0,1,2,3,1]

There are five keys less than 2. So the first 2 will go in position 5 in the output.

Output = [0,1,1,1,1,2,2,3,3,4]

Counting the frequencies

The frequency of each key can be computed using a bookkeeping array with size equal to k+1 intialized with zeros.

Since the keys in the input array are in the range [0,k], we can iterate over it and use the keys as indices for the bookkeeping array.



During the iteration we increment the elements of the bookkeeping indexed by the keys.

At the end, each element of the bookkeping array will store the frequency of the key with the corresponding index.

The construction of the bookkeeping array takes O(n) time. Build the sorted output

If the input array contains only integer keys without any attached value, it is trivial to build the sorted output.

We can just iterate through the bookkeeping array and fill the sorted output with the occurrences of each key.



The generic case where the input elements are key-value pairs is more complicated.

It is necessary to precompute the position of each input element in the sorted output.

The easiest way is to accomplish this is building up another array.

👇

We can use the bookkeeping array to build up an array that will tell us where the next occurrence of a key goes in the sorted output.

We can call this array next_index because its i-th element represents the position of the next input element with key i in the sorted output. How can we build the next_index array?

1️⃣ the output position of the first element with key i corresponds to the number of elements with key < i

2️⃣ the bookkeeping subarray with indices in the range [0,i-1] contains the frequencies of all the elements with key < i

So the i-th element of the next_index array corresponds to the cumulative sum of the bookkeeping array up to the index i-1.

Notice how the bookkeeping and the next_index arrays have the same size.

The last step is now using the next_index to build the sorted output.



We can now iterate through the input array and use each key as an index for the next_index array to get its position in the output array.

Once the current element is placed in its output position, the next_index element indexed by its key get increased. Space optimization

A careful reader could have already noticed this.

We could actually avoid to build up the next_index array and use directly the bookkeping array saving some memory space. To understand how, let's consider that:

1️⃣ the position of the last element with key i corresponds to the number of elements with key <= i

2️⃣ the bookkeeping subarray with indices in the range [0,i] contains the frequencies of the elements with key <= i

So the cumulative sum of the bookkeping array up to the index i corresponds to the position of the last input element with key i in the sorted output (+1).

The cumulative sum of the bookkeping array can be computed in place.

The last step is to build the sorted output. We can iterate backwards over the input array and use each key as an index for the bookkeping array to get its position in the output array.

Before the current element is placed in its output position, the bookkeping indexed by its key get decreased.



Extension

We always assumed that the range of key is [0,k], but actually this is not a prerequisite.

We can apply the counting sort to whatever integer range of keys.

The trick is just to find the minimum element and store the frequency of that minimum element at 0 index. Asymptotic Analysis

Time complexity = O(n+k) to iterate through both the input array and the bookkeeping array.

Space Complexity = O(k) to store the bookkeeping array. Stability

An important property of counting sort is that it is stable.

Elements with the same key will appear in the output array in the same order as they do in the input array.
