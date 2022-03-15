https://twitter.com/Franc0Fernand0/status/1473628051397398535?s=20&t=kObvIjelj9qDiu4mJE-FGg

𝗥𝗲𝗻𝗱𝗲𝘇𝘃𝗼𝘂𝘀 𝗵𝗮𝘀𝗵𝗶𝗻𝗴 is a great algorithm:

➠ it solve the distributed hashing problem
➠ it is less famous than consistent hashing
➠ it is easier to grasp and likewise performing

Let's do justice to this algorithm.

// THREAD // 🧵

⟱ ⟱ ⟱

Distributed hashing problem

The problem is to map keys to a set of servers.

Keys are usually sharded data or clients requests.

The mapping should have 2 properties:

➠ adding/removing a server is not expensive
➠ keys are balanced in number between servers

Rendezvous hashing approach

The basic idea is simple:

➠ calculate a ranking of all servers for each key

➠ assign to a key the server with highest ranking

➠ mantain the mapping (key, highest ranking server) when adding and removing servers

Why it works ?

When adding or removing a server S:
➥ only the keys for which S has highest ranking are affected

When removing S:
➥ the keys are assigned to the 2nd server in their list

When adding S:
➥ the keys for which S is 1st in the ranking are assigned to S

How is it implemented ?

➠ hash the key together with the server to get a unique list of servers for that key

➠ sort the servers using the hash values

➠ assign the key to the first server

Query time for each key

Rendezvouz hashing takes typically O(N) for N servers.

Why ?

It is necessary to calculate the hash for each key-server combination. Memory requirements

Rendezvous hashing doesn't require storing any additional data.

The ranking is calculated on the fly for each key. Use cases

With a good hash function, rendezvous hashing gives an even distribution of the keys also when adding and removing servers.

It's a good algorithm to load balance medium-sized distributed systems, where an O(N) lookup cost is acceptable.
