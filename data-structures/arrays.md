๐งฑ Arrays in a nutshell ๐งฑ

โข intro
โข indexing
โข static vs dynamic
โข multidimensional arrays
โข advantages & disadvantages
โข main operations & time complexity

A data structure thread ๐งต โ

Introduction

โ An array is a contiguous block of memory storing elements of the same type.

โ Primitive data structure, but a building block for many others (i.e. queues, stacks).

โ Linear data structure where the elements are stored sequentially

Indexing

โ elements can be accessed in costant time by using an integer index

โ the index of the first element is 0

โ the index of the other elements represent their offset to 0

โ accessing an index exceeding the array size cause a memory access error



Static vs Dynamic

โ Static arrays have fixed size that can never be changed. The number of elements they hold shall be defined in advance.

โ Dynamic arrays have the capability to resize when adding more elements. Typically a dynamic array doubles in size when it get full.



Multidimensional Arrays

โ arrays whose elements are arrays

โ the dimension is given by the number of nested arrays

โ elements are accessed using n indexes, one for each dimension

โ the total number of elements is computed multiplying the size of all the dimensions

โ a 2D array is used to represent a matrix, elements are accessed using 2 indexes

โ multidimensional arrays are still a single contiguous block of memory

โ A[50] is equivalent to A[10][5] where element are accessed using code like A[i + (5 * j)] instead of A[i][j]

Pros and cons

+ Fast lookups: retrieving an element at a given index takes O(1) time

+ Cache-friendly: elements are next to each other in memory, making an efficient use of cache

- Adding and removing elements is not possible for static arrays and slow for dynamic

Main operations

โ Access an element (r/w) using its index takes O(1) time

โ Add an element is not possible for static arrays or requires a right-shift all the elements on its right for dynamic. This takes O(n). โ Remove an element is not possible for static arrays or requires a or left-shift all the elements on its right for dynamic. This takes O(n).

โ Search for an item require to traverse the array in O(n). For sorted elements this can be reduced to O(logn) using binary search. โ appending an item is a valid operation only for dynamic arrays

โ when the array is full, each resizing takes O(n) time to copy all existing elements

โ but this happen so rarely that the amortized time of appending a new element is still O(1)
