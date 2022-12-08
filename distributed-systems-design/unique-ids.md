https://twitter.com/Franc0Fernand0/status/1543235128876564480?s=20&t=6dU-uE_Tuf7se1a62DaVhA

The backend of many large scale applications requires to generate unique IDs.

Some common possibilities are:

1. UUIDs
2. database generated IDs
3. service generating snowflake IDs

How do they work and differ ?

//Thread// ↓

{1/11}



Generating unique identifiers isn't a difficult task in a single node.

Some simple strategies could be:

1. use an incremental ID
2. use a function getting the time of the day

These strategies fail in a distributed environment, since they would create duplicated IDs.

{2/11}

A widely used solution in distributed systems are Universal Unique Identifiers (UUIDs).

UUIDs are 128-bit numbers that can be generated in a standard way at application level.

They are usually combined by several parts like time, node’s MAC address or MD5 hash.

{3/11}

The main benefits of UUIDs are:

1. large ID space, virtually eliminating collisions
2. uniqueness without any synchronization between distributed nodes

The main drawbacks are:

1. big size (128 bit)
2. not sequential IDs if generated by different nodes

{4/11}

A 2nd alternative is generating IDs at database level instead of application level.

Many databases provide an auto increment feature.

So a database server can be used to generate unique IDs.

This approach is also known as ticket service and has been used by Flickr.

{5/11}

The main benefits of database generated IDs are:

- the application code gets simpler

- IDs are sequential and short in size

The main drawbacks are:

- the additional round trip to get the IDs from the database

- the database becomes a single point of failures

{6/11}

The last problem can be mitigated using multiple servers.

For example server could generate even IDs and another odds IDs.

Round robin could be used to load balance between the servers and deal with down time.

Clearly the generated IDs drift a bit after a while.

{7/11}

A 3rd option is having a dedicated service generating snowflake Ids.

This form of unique IDs was introduced by Twitter and then adopted also by Discord and Instagram.

The main idea is to generate the IDs as a composition of multiple fields.

{8/11}

In the original implementation the fields were:

• 41-bit timestamp
• 10-bit worker ID
• 12-bit sequence number
• 1-bit reserved for future usage

Some observations: ↓

{9/11}

• the timestamp with ms resolution can work for 70 years after a starting epoch

• the worker ID can define both datacenter and machine ID. It's assigned by a coordination service (Zookeper)

• the sequence number support up to 4096 unique IDs per ms

{10/11}

Such way of generating IDs has many advantages:

• it's available, since can be implemented by 1024 machines

• it's scalable, since each machine can generate 4096 IDs per ms

• IDs are time sortable since the timestamp is in the higher order bits

{11/11}