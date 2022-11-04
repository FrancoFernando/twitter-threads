https://twitter.com/Franc0Fernand0/status/1522215291274416129?s=20&t=sxYbnZphDGn69nnXLuChIA

Arrays and Linked Lists are simple but fundamental data structures.

All advanced data structures use them as building blocks.

Choosing between them is a matter of trade offs.

The 7 factors you should consider.

1. Access

• Arrays are better if you need to access elements randomly or with indices. This is an O(1) operation.

• Linked Lists allow only sequential access to its elements, so accessing a specific element is a O(n) operation.

2. Size

• Linked Lists can be easily extended to add more elements and are better if the number of elements is not known in advance. 

• The size of Arrays is fixed at declaration time and you need to know exactly the amount of memory to allocate.

3. Memory usage

• Arrays have a smaller footprint since they don't need extra storage to point to next data items. 

• Linked Lists require that extra storage. This makes lists less optimal to store small data or if the amount of memory is a concern.

4. Update

• Inserting and deleting an element in Arrays require a reallocation of the whole memory. This is very expensive.

• Linked Lists are a better choice for these operations since they only require the allocating or deallocating the memory for a single element.

5. Search

• Arrays allow to execute efficiently both linear in O(n) and binary search in O(log n). I

• Linked Lists allow to execute efficiently only linear search.

6. Performance

• Sequential access of elements is faster on Arrays because of the locality of data access and the better usage of data caches. 

• Linked lists store elements in random memory location and receive almost no benefit from the cache.

7. Multi-threading

• Linked Lists are more suitable for multi-threaded implementations because insert and delete operations affect only a few nodes.

• It is also possible to create lock free Linked Lists using compare and swap (CAS) operations.
