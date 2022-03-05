https://twitter.com/Franc0Fernand0/status/1487443194585522184?s=20

Understanding data structures is essential for any software developer.

The 8 must to know are:

➔ Arrays
➔ Lists
➔ Stacks
➔ Queues
➔ Sets
➔ Trees
➔ Graphs
➔ Hash tables

Here is an introduction including time complexity of the main operations.

// THREAD // 🧵↓

Arrays

➔ Primitive data structure
➔ Values are all of the same type
➔ Linear data structure, fixed in size
➔ Values are stored consecutively in memory
➔ Building block for many other data structures
➔ Dynamic arrays are a variant that resize themselves when necessary

The average time complexity of the most common operations on arrays are:

➔ Access: O(1)
➔ Insertion: O(n)
➔ Deletion: O(n)
➔ Search: O(n)

Lists

➔ Linear collection of nodes
➔ Each node contain values and a pointer (or reference) to the next node
➔ Linear data structure, dynamic in size
➔ Base building block for other data structures
➔ Double Linked lists contain also a pointer to the previous node

The average time complexity of the most common operations on a single linked list are:

➔ Access: O(n)
➔ Insertion: O(1) provided reference to the previous node
➔ Deletion: O(1) provided reference to the previous and next nodes
➔ Search: O(n)

Queues

➔ Linear data structure, dynamic in size
➔ Can be backed by an array or by a linked list
➔ Process values according to a First in first out policy
➔ Can be implemented with different additional traits: double ended or circular queues
➔ Useful for processing tasks

Average time complexity of the most common operations on a queue are:

➔ Access: O(n)
➔ Insertion: O(1)
➔ Deletion: O(1)
➔ Search: O(n)

Stacks

➔ Linear data structure, dynamic in size
➔ Can be backed by an array, by a linked list or by a dequeue
➔ Process values according to a Last in first out policy
➔ Useful for parsing and undo operations

Average time complexity of the most common operations on a stack is:

➔ Access: O(n)
➔ Insertion: O(1)
➔ Deletion: O(1)
➔ Search: O(n)

Trees

➔ A recursive collection of nodes containing values
➔ Non-linear data structure, dynamic in size
➔ Values can be ordered and unordered
➔ Can contain unique and non unique values
➔ Can be balanced or unbalanced in height

Average time complexity of the most common operations on a balanced tree is:

➔ Access: O(log(n))
➔ Insertion: O(log(n))
➔ Deletion: O(log(n))
➔ Search: O(log(n))

Graphs

➔ Non-linear data structure, dynamic in size
➔ Consists of nodes (vertex) and edges between nodes
➔ Can store information on both edges and nodes
➔ Edges can be be directed or undirected
➔ Useful for modeling whatever relationship between data

Average time complexity of the most common operations on a graph represented as adjacency matrix is:

➔ Access: O(1)
➔ Search: O(1)
➔ Insertion: Edge: O(1), Vertex: O(|V|^2)
➔ Deletion: Edge: O(1), Vertex: O(|V|^2)

Hash tables

➔ Data structure mapping keys to values
➔ Math operations (hash function) maps each key to the spot with its value
➔ Unordered and dynamic in size
➔ Useful when quick lookup of values by keys is needed

Amortized time complexity of the most common operations on a hash table is:

➔ Access: O(1)
➔ Search: O(1)
➔ Insertion: O(1)
➔ Deletion: O(1)

Sets

➔ A kind of storage for unique values
➔ Dynamic in size
➔ Can be backed by a tree or a hash table
➔ Values can be ordered and unordered
➔ Useful for mantaining unique values of any kind
➔ The average time complexity is the one of the underlying structure
