https://twitter.com/Franc0Fernand0/status/1527289983039483904?s=20&t=6dU-uE_Tuf7se1a62DaVhA

There are 2 main trade-offs in distributed systems:

1. availability vs consistency

2. consistency vs latency

The PACELC theorem describes both.

{1/7}



Let's consider as example a single leader configuration of nodes.

The leader is responsible for all the read and write operations to guarantee consistency.

The followers replicate the master to guarantee availability and tolerance to failures.

{2/7}

The 1st part of the theorem says that:

"In case of network partitions (P) it is necessary to choose availability (A) or consistency (C)"

Indeed, if the leader is not reachable because of a network partition there are 2 options.

{3/7} keep availability, allowing clients to read from followers that are potentially not in synch

2. keep consistency, letting the operations that can't reach the leader fail

{4/7}

The 2nd part of the theorem says that:

"else (E) in case of no network partitions it is necessary to choose latency (L) or consistency (C)"

Indeed, to guarantee consistency the leader needs to check its role with a majority of followers before serving a request.

{5/7}

This is because by the time the leader receive a request, it might be no longer the leader.

And if it were to serve the request without being leader, the system wouldn't be anymore consistent.

So there are 2 options.

{6/7} keep consistency, allowing the leader to confirm is role with the followers

2. keep low latency, avoiding this time consuming confirmation step.

{7/7}
