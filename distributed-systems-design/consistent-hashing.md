https://twitter.com/Franc0Fernand0/status/1467496905471111186?s=20&t=wUtTLoeMZXaddLg-JvLeNw

Consistent hashing is a great technique used in countless distributed systems:

- Riak
- Cassandra
- Couchbase
- Amazon Dynamo

I already dedicated a thread to it.

But some of you found the concepts hard to digest.

Especially virtual nodes.

I'll make everything clear 🧵👇



A preliminary remark.

If you missed the first thread AND

if you're not familiar with the use of hashing in distributed systems

here is the link to it


Problem definition

We have a set of servers and we want to map keys (data or requests) to these servers.

The mapping should be such that:

1️⃣ keys are balanced in number between servers
2️⃣ adding/removing server is computationally cheap

Solution

Consistent hashing meets the above requirements.

The key idea is considering the space of possible hash values circular instead of linear.

We hash servers and keys to place them on that circle.

Then we assign each key to the first server in clockwise direction. Why is good?

It satisfy requirement 2️⃣.

If we add a server we need to remap only the keys that are placed between the previous server in the circle and the new one.

If we remove a server, all the keys stored on the that server are assigned the next one on the circle. Why is not yet optimal ?

It not satisfy requirement 1️⃣.

Why?

First, the keys usually are not uniformely distributed over the circle.

Second, adding and removing servers makes the keys distribution even more skewed towards some servers. Virtual nodes to the rescue

Virtual nodes are just placeholders for the servers placed over the circle.

Insted of having only N servers we have now N*V servers over the circle, where V is the number of placeholders for each server.

Why this help ? Because the circle is divided into multiple smaller ranges and the key distribution becomes more uniform.

The higher is the number of virtual nodes, tho most uniform is the key distribution. Implementation

Instead one hash function for each server, we use multiple functions: one for each virtual node.

A dedicated hash table will then map each virtual node to the corresponding physical server so that we can retrieve the server to which each key is assigned. Key - Server assignment

Given the hash value for a key, the assignment of the key to the closest clockwise virtual node on the circle using binary search.

The correspondence between the vnode and the physical server can be stored on a dedicated hash table. Advantages

Virtual nodes not only help to uniformely distribute the keys, but bring also the following advantages.

▶️ keys reassignments is faster because after adding or removing servers multiple physical servers are involved instead of one

▶️ virtual nodes can carry physical replicas of a server for fault tolerance

▶️ clusters with heterogeneous servers are more effective, because it is possible to assign a higher number of virtual nodes to powerful servers and a lower number to less powerful servers
