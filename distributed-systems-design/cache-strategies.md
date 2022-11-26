https://twitter.com/Franc0Fernand0/status/1533088152159719425?s=20&t=7ayvBEV_J7bzWL7Iz3_tgA

Caching is an easy and powerful ways to increase the performances of a system.

There are several caching strategies like:

1. Cache aside
2. Read through
3. Write through
4. Write back 
5. Write around

How do they differ ?
Which one to choose ?

1. Cache aside

• The application read the data directly from the cache

• If the data is in the cache (hit), it's returned to the client

• Otherwise (cache miss), the application retrieves the data from the database and then writes it to the cache

✅ good for read-heavy workloads

✅ database and cache are decoupled and can handle different data models

✅ lazy loading prevent the cache being loaded with unnecessary data

❌ stale data may be provided, without a proper expiration time

❌ many cache miss at the beginning

2. Read through

• Like read aside, but the application interacts only with the cache

• In case of a miss, the cache gets the data from the database and stores it, returning it to the application

✅ simpler application code
❌ require a custom plugin for fetching the data

3. Write through

•  The application write data to the cache 

•  The cache write immediately the data to the database

✅ data consistency between cache and database
✅ no data loss in case of cache crash
❌ higher latency for write operations

4. Write back

•  The application write data to the cache

•  The cache write asynchronously the data to the database

✅ good for write-heavy workloads (low latency)
✅ reduce the load on database 
✅ tolerant to database failures
❌ possible data loss in case of cache crash

5. Write around

•  The application write data directly to the database

• Only the data that is read get into the cache

✅ good for data written once and read less frequently (the cache store only re-read data)

❌ reading recently written data gives a miss (high latency)

None of the above is the best caching strategy.

All depends on the data and data access patterns.

A good general purpose strategy for read intensive application is the cache around one. 

Memcached and Redis are widely used caches implementing this strategy.

If you have instead write heavy workloads, a write back strategy is a good choice. 

DynamoDB Accelerator (DAX) is an example of cache combining both read/write through.

If you have data written once and read rarely (i.e. real time logs), write around could be a good fit.
