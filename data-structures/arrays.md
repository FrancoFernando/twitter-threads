https://twitter.com/Franc0Fernand0/status/1595434021076492288?s=20&t=VtHDVAlWR0fFxQJvbbztog

Arrays are the most basic type of data structure.

All there is to know about them: {1/10} ↓

Introduction

• An array is a contiguous block of memory storing elements of the same type

• It's a primitive data structure but a building block for many others (i.e., queues, stacks)

• It's a linear data structure where the elements are stored sequentially

{2/10}

Indexing 

• the elements can be accessed in constant time by using an integer index

• the index of the first element is 0 

• the index of the other elements represents their offset to 0

• accessing an index exceeding the array size causes a memory access error

{3/10}

Static vs. Dynamic

• Static arrays have fixed sizes that can't be changed. The number of elements they hold shall be defined in advance

• Dynamic arrays can resize when adding more elements. Typically a dynamic array doubles in size when it gets full

{4/10}

Multidimensional Arrays

• arrays whose elements are arrays

• the dimension is given by the number of nested arrays

• elements are accessed using an index for each dimension

• the total number of elements is computed by multiplying the size of all the dimensions

{5/10}

 a 2D array is used to represent a matrix; elements are accessed using 2 indexes

• multidimensional arrays are still a single contiguous block of memory

• A[50] is equivalent to A[10][5] where element are accessed using code like A[i + (5 * j)] instead of A[i][j]

{6/10}

Pros and cons

+ Fast lookups: retrieving an element at a given index takes O(1) time

+ Cache-friendly: elements are next to each other in memory, making efficient use of cache

- Adding and removing elements is not possible for static arrays and is slow for dynamic

{7/10}

Main operations

• Accessing an element (r/w) using its index takes O(1) time

• Adding an element is impossible for static arrays or requires a right-shift of all the elements on its right for dynamic. This takes O(n)

{8/10}

• appending an item is a valid operation only for dynamic arrays

• when the array is full, each resizing takes O(n) time to copy all existing elements 

• but this happens so rarely that the amortized time of appending a new element is still O(1)

{9/10}

• Removing an element is impossible for static arrays. For dynamic, it requires a left shift of all the elements on its right in O(n)

• Searching for an item requires traversing the array in O(n). For sorted arrays, this can be reduced to O(logn) with a binary search

{10/10}


