https://twitter.com/Franc0Fernand0/status/1597970712869879809?s=20&t=VtHDVAlWR0fFxQJvbbztog

Counting sort is an algorithm capable to stable sort an array in linear time.

How it works and when to apply it:  {1/9} ↓

Counting sort requires that the elements of the input array I have an integer key in a finite range.

The idea is to use each key's frequency to determine the index of the elements with that key in the sorted output array O.

{2/9}

Let's assume that the range is [0,k] and consider an element with key c <= k.

If we knew the number of elements with key < c, then:

- the index of the 1st element with key c in O would be m

- the index of the 2nd element with key c in O would be m+1

and so on

{3/9}

An example can clarify.

I = [1,1,2,4,3,0,1,2,3,1]

There are five keys < 2. So the first 2 will go in position 5 in O, and the second 2 will go in position 6

O = [0,1,1,1,1,2,2,3,3,4]

The frequency of each key can be computed using a bookkeeping array B.

{4/9}

B has size k+1 and it's initialized with 0's.

Since the keys range is [0,k], it's possible iterate over I and use the keys as indexes for B.

During the iteration the elements of B indexed by the keys gets incremented.

{5/9}

At the end of the iteration, each element B[i] stores the frequency of the key with index i.

B can be used to determine where each occurrence of a key goes in O.

Remember: the position of the 1st element with key c in O is the number of elements with key < c.

{6/9}

But this is the cumulative sum of the B's elements up to the index c-1.

Let's call N the array such that N[i] is the cumulative sum of B up to the index i-1.

It's possible to iterate over I and use each key as an index for N to get its position in O.

{7/9}

Once the element of I[i] is copied in O[N[i]],  N[i] gets increased.

The time complexity is O(n+k) to iterate through I, B, and N.

The space Complexity is O(k) to store B and N.

{8/9}

The assumption that the range of the keys is [0,k] is not a prerequisite.

Counting sort can be applied to whatever integer range of keys.

The trick is to find the minimum element and store the frequency of that element at index 0.

{9/9}
