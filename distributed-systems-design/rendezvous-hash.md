https://twitter.com/Franc0Fernand0/status/1473628051397398535?s=20&t=kObvIjelj9qDiu4mJE-FGg

๐ฅ๐ฒ๐ป๐ฑ๐ฒ๐๐๐ผ๐๐ ๐ต๐ฎ๐๐ต๐ถ๐ป๐ด is a great algorithm:

โ  it solve the distributed hashing problem
โ  it is less famous than consistent hashing
โ  it is easier to grasp and likewise performing

Let's do justice to this algorithm.

// THREAD // ๐งต

โฑ โฑ โฑ

Distributed hashing problem

The problem is to map keys to a set of servers.

Keys are usually sharded data or clients requests.

The mapping should have 2 properties:

โ  adding/removing a server is not expensive
โ  keys are balanced in number between servers

Rendezvous hashing approach

The basic idea is simple:

โ  calculate a ranking of all servers for each key

โ  assign to a key the server with highest ranking

โ  mantain the mapping (key, highest ranking server) when adding and removing servers

Why it works ?

When adding or removing a server S:
โฅ only the keys for which S has highest ranking are affected

When removing S:
โฅ the keys are assigned to the 2nd server in their list

When adding S:
โฅ the keys for which S is 1st in the ranking are assigned to S

How is it implemented ?

โ  hash the key together with the server to get a unique list of servers for that key

โ  sort the servers using the hash values

โ  assign the key to the first server

Query time for each key

Rendezvouz hashing takes typically O(N) for N servers.

Why ?

It is necessary to calculate the hash for each key-server combination. Memory requirements

Rendezvous hashing doesn't require storing any additional data.

The ranking is calculated on the fly for each key. Use cases

With a good hash function, rendezvous hashing gives an even distribution of the keys also when adding and removing servers.

It's a good algorithm to load balance medium-sized distributed systems, where an O(N) lookup cost is acceptable.
