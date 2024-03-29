https://twitter.com/Franc0Fernand0/status/1511693972829347843?s=20&t=sxYbnZphDGn69nnXLuChIA

Distributed databases replicate data across multiple instances.

But how is the data exchanged ?

There are 3 common replication techniques:

1. Statement-based 
2. Log Shipping 
3. Row-based 

[Thread] ↓

. Statement-based 

A db send the same statements it received to its replicas.

The replicas execute the same updates, trying to get the same results.

The pros of this approach is its simplicity ✅

The cons are non deterministic statements leading to different results ❌

Functions getting random numbers or the time give always different results.

The solution is to replace these function calls with fixed values but it’s hard to consider every case.

Another issue is that transactions for relational db need to succeed or abort on every replica.

2. Log Shipping 

Many databases write changes to a log file before being applying them.

This is mainly done to provide durability and atomicity (for relational db).

The log describes changes at very low level (bytes on disk) and is not made for humans.

Log Shipping transfers these logs to the replicas so that they can apply them.

The main cons of this approach are:

• it's not compatible with a multi master topology (multiple logs cannot be merged)
• it can be difficult to replicate logs generated by different db versions

3. Row based

Also this strategy is based on a log, but it uses a different log just for replication. 

This log includes enough information to uniquely identify:
• a row
• a set of changes to be performed on that row.

The pros is that this log is decoupled from the storage engine and can replicate data regardless of the db versions ✅

The cons is that it's necessary to create a specific log storing a lot of data ❌

If an update changes n row, the log contain n entries.
