Do you know what

1. Strings
2. Trees
3. Graphs
4. Subsets
5. Points
6. Polygons

have in common ?

[Thread] {1/8} ↓

The short answer is recursion.

Each instance of these objects is composed by smaller instances of the same type of objects.

The recursive decomposition stops to the simplest object of that type.

This is very important to define recursive algorithms.

Let's go deeper.

{2/8}

Strings

Deleting the 1st character from a string, we get a shorter string.

The base case is an empty string.

Strings are recursive objects.

{3/8}

Trees

Deleting the root of a tree, we get a set of smaller trees.

Deleting any leaf of a tree, we get a slightly smaller tree.

The base case is a single tree node.

Trees are recursive objects.

{4/8}

Graphs

Deleting any vertex from a graph, we get a smaller graph.

Dividing the vertices of a graph into 2 groups and cutting all edges between the 2 groups, we get 2 smaller graphs.

The base case is a single vertex.

Graphs are recursive objects.

{5/8}

Subsets

Consider all subsets made of the elements {0,...,n}.

If you delete the element n from each of those subset, you get all subsets made of the elements {0,..., n−1}.

The base case is a empty set.

Subsets are recursive objects.

{6/8}

Points

If you take a cloud of points, and you draw a line separating them into 2 groups, you get 2 smaller clouds of points.

The base case is a single point.

Sets of points are recursive objects.

{7/8}

Polygons

If you insert a diagonal between 2 nonadjacent vertices of a polygon, you get 2 smaller polygons.

The base case is a triangle.

Polygons are recursive objects.

{8/8}
