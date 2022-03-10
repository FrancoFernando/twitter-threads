https://twitter.com/Franc0Fernand0/status/1466335277367058433?s=20&t=wUtTLoeMZXaddLg-JvLeNw

There are 🔟 fundamental graph algorithms:

● bfs
● dfs
● max flow
● colouring
● matching
● shortest path
● cycle detection
● min spanning tree
● topological sorting
● strongly connected components

Explanation ➕ guide to their practical use cases.

A thread 🧵 ↧

1️⃣ Breadth-first search - Explanation

It's a traversal algorithm.

It starts at a given vertex and explores all its neighbours at the current level before moving on to the vertices in the next level.

It's implemented using a queue data structure. Breadth-first search - Use cases

● determine the shortest paths and minimum spanning trees in unweighted graphs

● build web pages indexes

● search on social networks

● find available neighbour nodes in peer-to-peer networks

2️⃣ Depth-first search - Explanation

It's a traversal algorithm.

It starts from a given vertex and explores as far as possible along each branch before retracing back.

It's implemented using a stack data structure. Depth-first search - Use cases

● find a path between 2 vertices

● detect cycles in a graph

● topological sorting

● solve maze puzzles

3️⃣ Shortest path - Explanation

Find a path between 2 given vertices such that the sum of the weights of the edges that should be travelled is minimum.

There are 2 main algorithms:

● Dijkstra
● Bellman–Ford

Shortest path - Use cases

● find directions to travel from one location to another in mapping software

● solve the min-delay path problem in networking

● determine the choices to reach a goal state via transitioning among different states

4️⃣ Cycle detection - Explanation

Detect if there is a path where the first and last vertices are the same.

There are 2 main algorithms:

● Floyd cycle detection
● Brent

Cycle detection - Use cases

● distributed message-based algorithms

● detect deadlocks in concurrent systems

● process large-scale graphs on a distributed cluster

● determine keys that can map a message to the same encrypted value. 5️⃣ Minimum spanning tree - Explanation

Find a subset of the edges that connects all the vertices with the minimum sum of weights without cycles.

There are 2 main algorithms:

● Prim
● Kruskal

Minimum spanning tree - Use cases

● image registration

● protocols to avoid network cycles

● analysis of graph-based data clusters

6️⃣ Strongly connected components - Explanation

Find subsets of vertices where each vertex is reachable from every other vertex.

There are 2 main algorithms:

● Kosaraju
● Tarjan

Strongly connected components - Use cases

● classify edges of bipartite graphs

● model checking in formal verification.

● find strongly connected groups of people in social networks and make recommendations based on common interests

7️⃣ Topological sorting - Explanation

Find a linear ordering the vertices in a DAG so that for each directed edge (x, y) in the ordering, vertex x comes before y.

There are 2 main algorithms:

● Kahn
● Depth-first search

Topological sorting - Use cases

● instruction scheduling

● data serialisation

● determine the order of compilation tasks

● resolve symbol dependencies in linkers

8️⃣ Graph colouring - Explanation

Assigns k colours to the vertices (or to the edges) while ensuring that any 2 adjacent vertices (or edges) don't have the same colour.

There are 2 main algorithms:

● Breadth-first search
● Depth-first search

Graph colouring - Use cases

● check if a graph is bipartite

● colour schedule timetable

● assign mobile radio frequencies

● colour geographical maps of countries

9️⃣ Maximum flow - Explanation

A graph can be also modeled as a flow network with edge weights as flow capacities. The maximum flow is a flow path that can obtain the maximum possible flow rate.

There are 3 main algorithms:

● Ford-Fulkerson
● Edmonds–Karp
● Dinic

Maximum flow - Use cases

● circulation demand problems

● airline flight crews scheduling

● discard teams that cannot reach the current leader given the remaining matches

● image segmentation to distinguish between background and foreground in an image

🔟 Matching - Explanation

Find subsets of edges that does not have common vertices.

There are 3 main algorithms:

● Hopcroft-Karp
● Hungarian
● Blossom

Matching - Use cases

● matchmaking between 2 sets of people
● resource allocation problems
● resource allocation and optimization in travel
