https://twitter.com/Franc0Fernand0/status/1469682304712859654?s=20&t=b_NKL_-ROHYRF7wgyY0rQw

9️⃣ tree data structures worth knowing:

➤ binary search tree
➤ red-black tree
➤ generic tree
➤ binary tree
➤ splay tree
➤ AVL tree
➤ B-tree
➤ Treap
➤ Trie

Brief introduction & guide to common practical use cases.

// Thread // 🧵

1️⃣ Generic tree - Description

A hierarchical data structure representing relationships between different nodes.

It can contain no nodes or 1 special node (root) with 0 or more subtrees.

Each node has only 1 parent node, but can have many children nodes. Generic tree - Use cases

There are no constraints on the hierarchical structure.

It is commonly to store whatever hierarchical data (i.e folder structures)

2️⃣ Binary tree - Description

Tree data structure where a node can have at most 2 child nodes.

The children of a node are known as the left and right child. Binary tree - Use cases

- used by compilers to build syntax trees

- used to implement expression parsing and evaluation

- used to store routing-tables link routers in a network

- used in data compression encoding algorithms

3️⃣ Binary Search Tree - Description

A constrained extension of a binary tree with a unique property.

Given a node, the value of its left child is less than or equal to the parent value.

The value of its right child is greater than or equal to the parent value. Binary Search Tree - Use cases

- used to implement simple sorting algorithms

- used to maintain a sorted stream of data

- used to implement double ended priority queues

- used in search applications where data are constantly entering and leaving

4️⃣ AVL tree - Description

A self-balancing binary search tree.

Each node has associated a value representing the difference in height between its left and right subtrees

After an operation, if these difference become more than 1, rotations are performed to balance the tree. AVL tree - Use cases

- used in every situation where frequent insertions in the tree are required

- used in the memory management subsystem of the Linux kernel to search memory regions of processes during preemption

5️⃣ Red-black tree - Description

A self-balancing binary search tree.

Each node is either red or black.

Root and leaves are black.

If a node is red, both its children are black.

Every path from a given node to any leaf must have the same number of black nodes. Red-black tree - Use cases

- used in computational geometry for reducing time complexity of the algorithms

- used to implementthe CPU process scheduler in Linux

- used in various implementations of associative data structures (i.e. C++ map, set, Java HashMap)

6️⃣ Splay tree - Description

A self-balancing binary search tree.

Recently accessed nodes are quick to access again.

After an insertion or search, an action called splaying rearrange the tree (using rotations) so that the involved element is placed as root. Splay tree - Use cases

- used to implement caches

- used in garbage collectors

- used in data compression

7️⃣ Treap - Description

A binary search tree mixing heap and trees.

Each node has a key and a priority.

The keys follow the binary-search-tree property.

The priorities (usually random values) follow the heap property. Treap - Use cases

- used to maintain authorization certificates in applications based on asymmetric cryptography

- used to perform fast set operations (i.e. union, intersect)

8️⃣ B-tree - Description

A self-balancing search tree containing multiple nodes which keep data in sorted order.

Each node has n keys (stored in ascending order) and n+1 children.

The keys separate the ranges of keys stored in each sub-tree

B-tree - Use cases

- used in database indexing to speed up the search

- used in file systems to implement directories

9️⃣ Trie - Description

A tree data structure whose nodes store the letters of an alphabet.

Each path from the root to leaves forms a word.

All the descendants of a node share a common prefix associated to that node. Trie - Use cases

- used in autocomplete word systems

- used to implement speel checkers

- used to solve word games
