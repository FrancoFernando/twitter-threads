https://twitter.com/Franc0Fernand0/status/1429003269951692801?s=20&t=kObvIjelj9qDiu4mJE-FGg

systems?

Check out this thread 🧵👇



The main idea of caching is to store data in a location that is different from the original one, so that it will be faster to access them.

You can imagine a cache like a fast short-term memory with a limited amount of space. Reading

When trying to read a data that is in the cache, you have a cache hit and you can retrieve it quickly.

When trying to read a data that is not in the cache, you have a cache miss and you need to retrieve it from its original location with higher latency. Writing

There are three main schemes that are used for writing operations: write through, write around and write back.

How do they differ? 👇 write through: data is written both to the cache and the original location.

✅ data is always consistent
✅ no data loss in case of cache crash
❌ high latency and low throughput for write operations write back: data is written only to the cache. The writing to the original location is done only at specific intervals or under certain conditions.

✅ low latency and high throughput for write operations
❌ data is not always consistent
❌ possible data loss write around: data is written only to its original location. The writing to the cache is done only after a cache miss.

✅ cache is not filled with data that will not subsequently be re-read
❌ reading recently written data generates a cache miss and has higher latency

Which is the best writing policy?

Generally speaking none of them: it really depends on your application’s requirements.

I personally prefer the write through technique since is the safest one, but there is no point in using this if you have a write intensive application. Eviction

Since the amount of space is limited, every cache needs a mechanism to remove data when the cache is full.

Here are the most common eviction policies: 👇

- First In First Out (FIFO): remove the first block accessed

- Last In First Out (LIFO): remove the block accessed most recently

- Least Recently Used (LRU): discard the least recently used items first

- Most Recently Used (MRU): evict the most recently used items first

👇

- Least Frequently Used (LFU): discard the items that are used least often first. Require to keep track of how often an item is needed.

- Random Replacement (RR): randomly select a candidate item and discards it to make space when necessary. 
- 
Caching occurs at many different levels of a distributed system: hardware, operating system, front end components, web applications, databases and so on.

Some examples? 👇

- at hardware level, CPU caches make it faster to retrieve data from memory
- clients can cache data so they don't need to request them to a server
- a server can cache data avoiding to query the database

In distributed system, caching is largely used to reduce the latency.

How?

- saving network requests
- storing the result of a computationally expensive operation executed on a server
- avoiding repeated operations (e.g. same database query executed by multiple servers)

Most of distributed systems uses (a combination of) two primary approaches to caching: application caching and database caching 👇

Application caching

Require an explicit integration in the application code itself.

The application code usually checks if a value is in the cache, retrieving the value from the database if not. Database caching

Every database provides some degree of caching that can be tweaked to meet the system’s access patterns.

This form of caching can generate a great performance improvement without requiring any change in the code. In-memory caching

Accesses to RAM are orders of magnitude faster than disk, so the most performant caches you can use in distributed systems are those storing all data in memory.

Some examples?

Memcached and Redis (Redis can also be configured to store some data to disk).
