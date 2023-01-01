https://twitter.com/Franc0Fernand0/status/1527289983039483904?s=20&t=6dU-uE_Tuf7se1a62DaVhA

The PACELC theorem describes 2 main trade-offs in distributed systems:

- availability vs consistency

- consistency vs latency

Here is the theorem and how to interpret it:

{1/6} ↓

The theorem has 2 parts:

"In case of network partitions (P), it is necessary to choose availability (A) or consistency (C)"

"else (E) in case of no  partitions, it is necessary to choose latency (L) or consistency (C)"

{2/6}

To understand the theorem, consider a cluster of machines with a single leader.

The leader executes all write operations, ensuring consistency.

The other machines are replicas that execute reads, ensuring availability and fault tolerance. 

{3/6}

If the leader is not reachable because of a network partition, there are 2 possibilities:

1. keep availability, allowing the clients to read from replicas potentially not in synch

2. keep consistency, letting fail all the read operations that can't reach the leader

{4/6}

But even in the case of no network partitions, there is a further consideration.

Before executing a write operation, the leader must check its role with a majority of replicas.

This is because it might not be the leader anymore by the time it executes a write.

{5/6}

And the system is consistent only if the machine executing a write operation is the leader.

So there are 2 options:

1. keep consistency, allowing the leader to check its role 

2. keep low latency, avoiding this time-consuming check

{6/6}
