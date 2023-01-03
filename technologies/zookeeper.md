https://twitter.com/Franc0Fernand0/status/1593984418015748096?s=20&t=VtHDVAlWR0fFxQJvbbztog

Apache Zookeeper is an extensively used coordination service for distributed systems.

This is how it works: {1/13} ↓

The simplest way to think about Zookeeper is as a distributed file system.

Indeed Zookeeper organizes information in a hierarchical way similar to a file system.

At the top, there's a root referred to as /, and below are nodes referred to as zNodes.

{2/13}

Each zNode may act as either a file containing binary data or a directory including other zNodes.

Of course, zNodes also have metadata like read & write permissions or version information.

Unlike an ordinary distributed file system, zNodes can be ephemeral or regular.

{3/13}

An ephemeral zNode disappears when the session of its owner ends.

A regular zNode is instead created and deleted explicitly by a client and can also be sequential.

In this case, the value of a monotonically increasing counter is appended to its name.

{4/13}

The sequential value of a node is never smaller than the value of one of its ancestor nodes.

ZooKeeper also gives the possibility of registering watchers on zNodes.

This allows clients to receive timely notifications of changes without requiring polling.

{5/13}

ZooKeeper provides a robust implementation of a few basic operations on ZNodes like:

• create and delete
• getData and setData
• exists
• getChildren
• sync

Using these APIs, it's possible to build many advanced patterns in distributed systems.

{6/13}

Let's see some examples of patterns.

1. Servers discovery

Each server publishes its IP address in an ephemeral node.

If a server loses connectivity with ZooKeeper and doesn't reconnect within the session timeout, its information is automatically deleted.

{7/13}

2.  Leader election

Each server publishes its information in a sequential and ephemeral zNode.

The server with the lowest sequential zNode is the leader.

If the leader goes offline, its ephemeral node is removed and all other servers can observe who is the new leader.

{8/13}

3. Message queue

Clients can register as watchers on a zNode for a specific topic.

Messages regarding that topic will be sent to all watchers by writing to that zNode.

Since watching a zNode is one shot, the clients need to register again after every message.

{9/13}

4. Configuration management

The configuration is stored in a zNode.

Processes start up with the path of that zNode and read their configuration. 

They also register as watchers of the zNode to be notified in case the configuration is updated.

{10/13}

From an architectural point of view, the zNodes tree is stored as an in-memory replicated database.

For recoverability, changes are logged to the disk before being applied to the in-memory database.

Read requests can be processed by any Zookeeper server.

{11/13}

Write requests are forwarded to a single server acting as leader.

The other servers receive change proposals from the leader through an atomic broadcast protocol.

This protocol (Zab) uses a simple majority quorum to decide on each proposal.

{12/13}

The Zab protocol guarantees that every update is part of a total ordering. 

All clients might not be at the same point in time, but they see updates in the same order.

So, ZooKeeper puts correctness and consistency first and speed second.

{13/13}

