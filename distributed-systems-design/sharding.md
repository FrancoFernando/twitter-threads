https://twitter.com/Franc0Fernand0/status/1515331015639801862?s=20&t=6dU-uE_Tuf7se1a62DaVhA

Data sharding means splitting a database into multiple pieces or shards.

A primer on data sharding.

1. when to use it
2. how to partition the data
3. benefits and disadvantages

{0/9} ↓

There are 2 main reasons to shard a database:

1. the working data set is too large and the memory necessary to store it exceeds the capacity of a machine

2. the volume of writes is so high that a single server (or a set of replicas) can’t keep up with them.

{1/9}

Why a simple data replication is not effective in the 2nd scenario?

The reason is that it's not possible to run a subset of writes on each node like for reads.

All the writes needs to run on all the databases.

{2/9}

There are 4 popular schemes schemes to decide how to shard a database into multiple smaller DBs.

Vertical Partitioning
Hash Based Partitioning
Range Based Partitioning
DirectoryBased Partitioning

{3/9}

Vertical

The data is logically divided to store tables related to a specific feature in their own server.

✅ architecturally simple and straightforward to implement

❌ in case of additional growth it may be necessary to further partition a feature specific DB

{4/9}

Hash Based

Give some values as input to a hash function to determine to which db the data should go.

✅ a good hash function balance the load across the databases

❌ adding or removing a db means reashing values and migrating data with possible downtimes

{5/9}

Range Based

Split the data based on ranges of a certain value.

i.e. sales transactions split by year or users split by zip code.

✅ simple to implement and facilitate data scan and range queries

❌ lead to unbalanced load (hotspots) if ranges aren't chosen carefully

{6/9}

Directory Based

The partition scheme is stored in a lookup service abstracting it from the application.

✅ it's flexible. Changing partition scheme or number of db has no impact on the application

❌ it's complex and connecting to the service impact the performances

{7/9}

Advantages of data sharding

1. Less data in each partition allows faster querying

2. Writing in parallel on different shards increase the write throughput

3. More availability since if one shard goes down the others still operate

{8/9}

Disadvantages

1. The complexity increases and applicative code can be necessary to handle sharding logic

2. Operations like back up, indexing, changing schema are more difficult

3. joins are not efficient since data has to be compiled from multiple db.

