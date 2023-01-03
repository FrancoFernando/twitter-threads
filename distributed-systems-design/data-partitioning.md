https://twitter.com/Franc0Fernand0/status/1604131437430689796?s=20&t=VtHDVAlWR0fFxQJvbbztog

Partitioning is the process of storing a large database across multiple machines.

Here are the popular partitioning architectures with their benefits and costs: {1/8} ↓

There are 2 strategies for partitioning a table: vertical and horizontal.

Vertical partitioning moves some columns to new tables.

It's straightforward and puts together data related to specific features.

But in case of growth, a further partition is required.

{2/8}

Horizontal partitioning divides a table into new tables with the same columns but fewer rows.

Each new table represents a different data store.

There are 3 popular schemas to horizontally partition (or shard) a table:

• hash-based
• range-based 
• directory-based

{3/8}

Hash-based applies a hash function to one or more columns to map rows to new tables.

A good hash function can balance the load across the new tables.

But adding or removing a data store means reashing values and migrating data.

{4/8}

Range-based splits the data using ranges of values in one or more columns.

It's simple to implement and facilitate data scan and range queries.

But it can generate an unbalanced load between tables if ranges aren't chosen carefully.

{5/8}

Directory-based uses a dedicated lookup service to store the partition schema.

It's flexible because it abstracts the schema and the number of data stores from the application.

But it's more complex, and connecting to the service impacts the performance.

{6/8}

The benefits of sharding are:

• horizontally scaling a database is easier

• reading and writing in parallel on multiple data stores increase the throughput

• availability increases since if one data store goes down, the others still operate

{7/8}

The disadvantages of sharding are:

• the complexity increases and application code is needed to fetch the data

• operations like back up, indexing, and changing schema are more difficult

• joins are inefficient since data has to be compiled from multiple data stores

{8/8}



