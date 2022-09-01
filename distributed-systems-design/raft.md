Sometimes in distributed systems a node needs to act has a leader with special powers like:

- accessing shared resources
- assigning work to other nodes
- taking care of write operations

Raft is a popular algorithm to elect a leader.

How does it work ?

//Thread// ↓ {1/9}



Electing a leader in a distributed environment is not a trivial task.

Indeed a good leader election algorithm needs to have 2 features:

1. safety: at most one leader shall be active

2. liveness: a leader shall be elected even if failures occurr

{2/9}

Raft is a leader election algorithm that guarantees these properties.

It makes 2 assumptions.

The 1st one is that time is divided into slots of arbitrary length called election terms.

Terms are numbered using logical timestamps (e.g. consecutive integers).

{3/9}

The 2nd one is that at a given time each node can be in one of 3 states:

- the leader state
- the follower state
- the candidate state

This makes possible implementing the algorithm as a state machine.

{4/9}

A node in the follower state recognizes another node as a leader.

It expects to receive from the leader a periodic heartbeat with the term when it was elected.

If this is not received within a timeout the node moves to the candidate state.

{5/9}

A node in the candidate state increments the current term and starts a new election.

It sends to all other nodes a request to vote for it, specifying the current term.

It also votes for another candidate using a first comes first served policy.

{6/9}

At the beginning all nodes are followers.

They don't receive any heartbeat and move to candidates.

From a candidate point of view, an election finishes for 3 possible events.

1. The candidate is voted by the majority of the other nodes and becomes the leader.

{7/9}

The candidate receives an hearbeat from another node that won the election.

If the term specified in the hearthbeat is >= than the candidate current term:

- the other node is recognized as a leader
- the candidate moves to follower state

{8/9}

The election term time slot finishes without a candidate receiving the majority of the votes.

In this case a new election is started randomly choosing its duration within an interval.

This reduces the probability of another election without a winner.

{9/9}
