https://twitter.com/Franc0Fernand0/status/1501562354173194244?s=20&t=dmvRoK3OHFyahOrajxZ3MA

Relational databases and key-values noSQL databases make up 85% of the market.

But for some systems, it's more effective using specialized storages like:

1. time series
2. blob storages
3. graph databases
4. spatial databases

How and why are they used ?

[Thread] ↓↓

Time series

Specialized storages for large amount of data related to a specific time.

They are optimized to measure data changes over time, performing statistic computations like rolling average, local min or max, aggregation.

Mainly used for monitoring purposes. Typical use cases:

- monitoring parts of the system with many events at a given time
- IOT systems with huge number of devices computing telemetry data
- dealing with financial data (stock, cryptocurrencies)

Popular implementations:

- InfluxDB
- Kdb+
- Prometheus

Blob storages

Specialized storages for storing and retrieving massive amounts of unstructured data that wouldn fit into a relational database.

Blob is indeed an acronym for binary large object including images, video files, large text data and compiled code. These databases are quite complex.

From user perspective, they look like key-value storages because data is usually accessed through a key.



Usually optimized for availability and durability.

Popular implementations:

- Google cloud storage
- Amazon S3
- Azure blob storage

Graph databases

Specialized storages for storing data with many relationships.

Data are stored according to the concept of graph data model with entities and relations between them.

Executing queries on these graphs looks like traversing a graph. Executing the same queries on relational databases would be much more complicated and costly because of the many joins between different tables.

The most popular graph database implementation is Neo4j coming with its own query language called Cypher. Spatial databases

Specialized storages for storing spatial data like locations on a map and performing spatial related queries.

They rely on the concept of spatial indexes like kdtree, m-tree, quadtree.

Quadtrees are the simplest and are conceptually similar to a grid. The outer grid rectangle represents the root and contains all the possible spatial locations.

Each rectangle is recursively divided into 4 and the quadrant represents the children of a node.

The division stops in quadrants with less than a specific number of locations. So geographical areas with many locations are divided in more quadrants.

Spatial queries using quadtrees are efficient, requiring base 4 logarithmic time.

Databases with good geospatial support are:

- postgreeSQL
- MongoDB
- ElasticSearch
