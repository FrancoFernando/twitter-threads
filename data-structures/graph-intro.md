https://twitter.com/Franc0Fernand0/status/1466335277367058433?s=20&t=wUtTLoeMZXaddLg-JvLeNw

There are π fundamental graph algorithms:

β bfs
β dfs
β max flow
β colouring
β matching
β shortest path
β cycle detection
β min spanning tree
β topological sorting
β strongly connected components

Explanation β guide to their practical use cases.

A thread π§΅ β§

1οΈβ£ Breadth-first search - Explanation

It's a traversal algorithm.

It starts at a given vertex and explores all its neighbours at the current level before moving on to the vertices in the next level.

It's implemented using a queue data structure. Breadth-first search - Use cases

β determine the shortest paths and minimum spanning trees in unweighted graphs

β build web pages indexes

β search on social networks

β find available neighbour nodes in peer-to-peer networks

2οΈβ£ Depth-first search - Explanation

It's a traversal algorithm.

It starts from a given vertex and explores as far as possible along each branch before retracing back.

It's implemented using a stack data structure. Depth-first search - Use cases

β find a path between 2 vertices

β detect cycles in a graph

β topological sorting

β solve maze puzzles

3οΈβ£ Shortest path - Explanation

Find a path between 2 given vertices such that the sum of the weights of the edges that should be travelled is minimum.

There are 2 main algorithms:

β Dijkstra
β BellmanβFord

Shortest path - Use cases

β find directions to travel from one location to another in mapping software

β solve the min-delay path problem in networking

β determine the choices to reach a goal state via transitioning among different states

4οΈβ£ Cycle detection - Explanation

Detect if there is a path where the first and last vertices are the same.

There are 2 main algorithms:

β Floyd cycle detection
β Brent

Cycle detection - Use cases

β distributed message-based algorithms

β detect deadlocks in concurrent systems

β process large-scale graphs on a distributed cluster

β determine keys that can map a message to the same encrypted value. 5οΈβ£ Minimum spanning tree - Explanation

Find a subset of the edges that connects all the vertices with the minimum sum of weights without cycles.

There are 2 main algorithms:

β Prim
β Kruskal

Minimum spanning tree - Use cases

β image registration

β protocols to avoid network cycles

β analysis of graph-based data clusters

6οΈβ£ Strongly connected components - Explanation

Find subsets of vertices where each vertex is reachable from every other vertex.

There are 2 main algorithms:

β Kosaraju
β Tarjan

Strongly connected components - Use cases

β classify edges of bipartite graphs

β model checking in formal verification.

β find strongly connected groups of people in social networks and make recommendations based on common interests

7οΈβ£ Topological sorting - Explanation

Find a linear ordering the vertices in a DAG so that for each directed edge (x, y) in the ordering, vertex x comes before y.

There are 2 main algorithms:

β Kahn
β Depth-first search

Topological sorting - Use cases

β instruction scheduling

β data serialisation

β determine the order of compilation tasks

β resolve symbol dependencies in linkers

8οΈβ£ Graph colouring - Explanation

Assigns k colours to the vertices (or to the edges) while ensuring that any 2 adjacent vertices (or edges) don't have the same colour.

There are 2 main algorithms:

β Breadth-first search
β Depth-first search

Graph colouring - Use cases

β check if a graph is bipartite

β colour schedule timetable

β assign mobile radio frequencies

β colour geographical maps of countries

9οΈβ£ Maximum flow - Explanation

A graph can be also modeled as a flow network with edge weights as flow capacities. The maximum flow is a flow path that can obtain the maximum possible flow rate.

There are 3 main algorithms:

β Ford-Fulkerson
β EdmondsβKarp
β Dinic

Maximum flow - Use cases

β circulation demand problems

β airline flight crews scheduling

β discard teams that cannot reach the current leader given the remaining matches

β image segmentation to distinguish between background and foreground in an image

π Matching - Explanation

Find subsets of edges that does not have common vertices.

There are 3 main algorithms:

β Hopcroft-Karp
β Hungarian
β Blossom

Matching - Use cases

β matchmaking between 2 sets of people
β resource allocation problems
β resource allocation and optimization in travel
