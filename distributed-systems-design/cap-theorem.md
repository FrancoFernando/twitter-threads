There are 3 desirable properties for any distributed system:

1. Consistency
2. Availability
3. Partition tolerance

The CAP theorem states that only 2 out of the 3 are achievable.

What are these properties ?

Which are the possible combinations ?

{1/8}

Consistency

All the nodes shall:

- see an up-to-date copy of the data at the same time
- get the most recently written data after a read operation

This is true only if all nodes see the same set of updates in the same order.

{2/8}

Availability

All the nodes shall:

- receive a response to a request even if this could not contain the most recent data

This is true only if every request terminate, even in case of critical network failures,

{3/8}

Partition Tolerance

The system shall continues to operate even if:

- an arbitrary number of nodes fails
- an arbitrary number of messages is lost or delayed

This is true only if the data is replicated enough across nodes and networks.

{4/8}

Not all combinations are possible.

Why ?

The system can't guarantee both Consistency and Availability if it's not partition tolerant.

If a network get partitioned, the updates from a partition are not propagated to the other.

So there are only 2 possibilities

{5/8}

Consistency - Partition tolerance

The only way to guarantee Consistency is to stop serving requests from one of the 2 partitions.

This means dropping Availability, since not all nodes are available anymore.

{6/8}

Availability - Partition tolerance

The only way to guarantee Availability is continuing serving requests from the 2 partitions.

This means dropping Consistency, since the nodes in each partition cannot receive updates from nodes in the other partition.

{7/8}

Since only the CP and AP combinations are possible, the CAP thorem can be formulated as follow:

"In case of network partitions, a distributed system can guarantee either Consistency or Availability".

{8/8}
