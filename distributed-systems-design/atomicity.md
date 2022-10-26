Atomicity is a fundamental property of database transactions.

It guarantees that all or none of the transaction's operations complete successfully. 

Two main techniques used to implement atomic transactions: {1/9} ↓

When a database executes an atomic transaction there are 2 possibilities:

1. the transaction executes successfully all the operations and commit

2. the transaction aborts because of a failure and rolls back all the performed changes

{2/9}

In a single database, atomicity is implemented recording all the changes in a write ahead log.

This log is persistently stored on the disk before applying the changes to ensure also durability.

{3/9}

The WAL log contains enough information to undo all the changes made by a transaction.

This means that each entry of the log includes at least:

- the id of the transaction
- the id of the modified object
- the old and new value of the object

{4/9}

WAL-based mechanisms are enough to guarantee atomicity in a single database.

But they're not enough when the transaction's operation involve multiple databases.

A commonly used technique in those cases is the two-phase commit protocol.

{5/9}

The protocol expects that an entity acts as coordinator while the others are partecipants.

The role of the coordinator is orchestrating the actions of the partecipants.

Usually the coordinator is the client executing the transaction.

The protocol has 2 phases.

{6/9}

1. Prepare

Before committing a transaction the coordinator sends a prepare request to all the partecipants.

Each partecipant answers if it's able or not to commit.

After answering, it needs to stop any activity untill the coordinator sends further instructions.

{7/9}

2. Commit

If all partecipants are ready, the coordinator sends them a commit request.

Otherwise it sends a request to abort.

Sending a commit request is a point of no return:

- coordinator can't change its mind anymore
- partecipants have to commit no matter what

{8/9}

2PC protocol guarantees atomicity in a distributed scenario, but it has some cons:

- it's slow requiring multiple round trips to complete

- it's not resilient since a transaction gets blocked if one of the parts fails

Replication is necessary to increase resiliency.

{9/9}




