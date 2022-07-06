https://twitter.com/Franc0Fernand0/status/1505199986941874178?s=20&t=dmvRoK3OHFyahOrajxZ3MA

Modern applications are centered around data.

This is why distributed systems replicate data.

→ How happen data replication ?
→ What are the benefits of replicating data ?

[Thread] {1/9} ↓↓

The idea of replication is to have duplicated versions of a database (replicas).

When the a database goes down, one of the replicas takes over.

There are 3 main advantages of duplicating data with replicas.

{2/9} reduce the system latency, keeping the data closer to the users

2. increase the system throughput, adding more machines able to serve requests

3. increase the system availability, having ready to use copies of the data in case of failures

{3/9}

Replication is possible only if the replicas are up to date with each other.

Updates can happen in 2 ways:

SYNCHRONOUSLY: writes complete only when data is stored on all the replicas

ASYNCHRONOUSLY: writes complete as soon as the data is written on a database.

{4/9}

The choice between the type of updates it's a matter of trade-offs.

Asyncronous replication trades data consistency and durability for better latency.

Syncronous replication trades performance and availability for data consistency.

Let's consider 2 different scenarios.

{5/9}

Scenario 1

We want to increase the system availability, tolerating regional failures.

If all the replicas are geographically close, we don't have high round trip times.

So we can accept that each write takes a bit longer to synchronously update all replicas.

{6/9}

Scenario 2

We want to reduce the system latency duplicating the data in different geographical areas.

In this case we have high round trip times among the replicas.

So asynchronous updates are better if we can accept that the data are not consistent in all replicas.

{7/9}

An intermediate way of executing updates is semi-synchronous replication.

There you can define define a number of replicas to replicate synchronously, while the others just use the asynchronous approach.

{8/9}

Data replication is a complex topic and I just scratched the surface here.

Other relevant points to understand are:

- different data replication topologies
- how data is actually replicated at low level

I'll cover these points in separated threads.

{9/9}
