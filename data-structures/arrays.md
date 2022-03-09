🧱 Arrays in a nutshell 🧱

• intro
• indexing
• static vs dynamic
• multidimensional arrays
• advantages & disadvantages
• main operations & time complexity

A data structure thread 🧵 ↓

Introduction

➔ An array is a contiguous block of memory storing elements of the same type.

➔ Primitive data structure, but a building block for many others (i.e. queues, stacks).

➔ Linear data structure where the elements are stored sequentially

Indexing

➔ elements can be accessed in costant time by using an integer index

➔ the index of the first element is 0

➔ the index of the other elements represent their offset to 0

➔ accessing an index exceeding the array size cause a memory access error



Static vs Dynamic

➔ Static arrays have fixed size that can never be changed. The number of elements they hold shall be defined in advance.

➔ Dynamic arrays have the capability to resize when adding more elements. Typically a dynamic array doubles in size when it get full.



Multidimensional Arrays

➔ arrays whose elements are arrays

➔ the dimension is given by the number of nested arrays

➔ elements are accessed using n indexes, one for each dimension

➔ the total number of elements is computed multiplying the size of all the dimensions

➔ a 2D array is used to represent a matrix, elements are accessed using 2 indexes

➔ multidimensional arrays are still a single contiguous block of memory

➔ A[50] is equivalent to A[10][5] where element are accessed using code like A[i + (5 * j)] instead of A[i][j]

Pros and cons

+ Fast lookups: retrieving an element at a given index takes O(1) time

+ Cache-friendly: elements are next to each other in memory, making an efficient use of cache

- Adding and removing elements is not possible for static arrays and slow for dynamic

Main operations

➔ Access an element (r/w) using its index takes O(1) time

➔ Add an element is not possible for static arrays or requires a right-shift all the elements on its right for dynamic. This takes O(n). ➔ Remove an element is not possible for static arrays or requires a or left-shift all the elements on its right for dynamic. This takes O(n).

➔ Search for an item require to traverse the array in O(n). For sorted elements this can be reduced to O(logn) using binary search. ➔ appending an item is a valid operation only for dynamic arrays

➔ when the array is full, each resizing takes O(n) time to copy all existing elements

➔ but this happen so rarely that the amortized time of appending a new element is still O(1)
