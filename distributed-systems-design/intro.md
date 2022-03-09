Do you want to get a strong knowledge of distributed systems ❓

Are you preparing for system design interviews ❓

Here is a COMPLETE roadmap with the 2️⃣0️⃣ must to know concepts.

I will write dedicated posts to help you mastering these topics.

Don't miss this thread 🧵 👇

1️⃣ Network Protocols

You need to understand how machines in a distributed system communicate with each another.

So knowledge of low-level networking concepts is essential.

IP, TCP, UDP, DNS and HTTP protocols are the bare minimum you need to know. 2️⃣ Storage

Information storage is a complex topic that is of crucial importance to design a distributed system.

You need to understand the difference between volatile and non volatile memory.

And you need to be familiar with the concept of database. 3️⃣ Availability

Most of distributed systems need to be high available.

So you need to know:

▶️ how you can measure the availability of a system
▶️ how you can increase the availability of a system through redundancy

4️⃣ Cache

Caches are used to store responses of network requests or results of computationally expensive operations.

You need to get familiar with the cache hit and miss terminology and with cache eviction policies.

You should also know what is a Content Delivery Network. 5️⃣ Latency and Throughput

These are key parameters to evaluate the performances of a distributed system.

Knowing the latencies of the most common operations is extremely useful for back of the envelope calculations. 6️⃣ Proxies

Proxies are intermediary servers playing a huge role in every real system.

Be sure to clearly understand the difference betweeen forward and reverse proxies. 7️⃣ Load Balancers

They are a kind of reverse proxies that distribute traffic across several servers.

You can place them in many places while designing a distributed systems.

You should know the different server selection strategies a load balancer can use. 8️⃣ Hashing

Hashing is mainly useful in 2 scenarios: elastic scaling of cache servers and data partitioning.

There are 2 must to know techniques: consistent hashing and rendezvous hashing. 9️⃣ Relational Databases

These are structured databases storing data in tabular format and supporting SQL queries.

You should know what ACID transactions are, what is indexing and which is the difference between strong and eventual consistency. 1️⃣0️⃣ Key-Value Databases

These are non relational databases often used for caching and dynamic configuration.

You should know about popular key-value databases like: ETCD, Reddis and Zookeeper. 1️⃣1️⃣ Other Non Relational Databases

You should get familiar with the concepts of:

- blob storage (GCS, S3)
- graph database (Neo4j)
- time series database (Prometheus)
- spatial databases and quadtrees

1️⃣2️⃣ Replication And Sharding

Replication is the process of duplicating data across multiple servers to increase system redundancy.

Sharding is the process of dividing the data across multiple servers to increase system throughput.

Implementing them is very challenging. 1️⃣3️⃣ Leader Election

This is the process used in a cluster of server to select a leader server responsible of all the primary operations.

You should know about the most popular consensus algorithms used to select a leader (Paxos and Raft). 1️⃣4️⃣ Polling and Streaming

Polling is the process of fetching data or resources at regular intervals.

Streaming is the process of continuously getting a feed of information from a server.

You should definitely know about these 2 concepts. 1️⃣5️⃣ Logging and Monitoring

You need to have an idea about how to collect and store useful information about events in a system using logs.

You should also know how to get visibility of the system key metrics and aggregate them in a human readable form. 1️⃣6️⃣ Publish Subscribe Pattern

It is important to know how this popular messaging model works and be familiar with the concept of idempotent operations.

You should also know about frameworks like Apache Kafka and Cloud Pub/Sub. 1️⃣7️⃣ Peer-To-Peer

A peer to peer network is a set of machines splitting a workload between them to complete it in the fastest possible way.

You should have an idea about:

▶️ how they work
▶️ where they are used
▶️ what is a gossip protocol

1️⃣8️⃣ Rate Limiting

You should know how to limit the number of requests sent to or received by a system.

This is essential to prevent DDos attack trying to damage the system.

It's interesting to know how to use Redis to implement rate limiting strategies. 1️⃣9️⃣ MapReduce

This is a very popular framework to process very large distributed datasets efficiently and in a fault tolerant way.

Other than with MapReduce, you be familiar with the concept of distributed file system and its popular implementations (GFS and HDFS). 2️⃣0️⃣ API Design

You should know the basics of Web API design.

And be familiar with the concept of CRUD operations.
