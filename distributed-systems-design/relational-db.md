https://twitter.com/Franc0Fernand0/status/1486731467933683728?s=20&t=x02dA7LmrZctl5AWPMW71w

Relational databases for system design interviews.

Everything you need to know:

→ definitions
→ ACID transaction
→ database indexes
→ when to chose them

// THREAD // 🧵 ↓

Definitions

Relational databases imposes on the data a tabular like structure.

Data is stored in form of table and each table represents a specific entity.

The columns represent attributes of the entity.

The rows (or records) are instances of the entity. All tables are defined according to a specific schema (a set of rule and every record needs to be conform to the schema.

Most of relational databases support SQL (Structured Query Language).

SQL enables powerful queries to retrieve data on relational databases. Theoretically it would be possible to implement complex queries on application side using a programming language.

But large scaled distributed systyems have TB of data and to query that data you should load them in memory.

This is often non trivial or impossible. ACID Transaction

It is a combination of operations that satisfy 4 properties:

➤ Atomicity: all the operations are treated as a unit and they will all succeed or fail. If only 1 fails (i.e. because of a network error) all fail, the entire transaction is rolled back. ➤ Consistency: any transaction shall be conform to the database rules and any future transaction shall take into account any past one.

There is no stale state when a transaction is executed and another transaction doesn't know that the 1st one is executed. ➤ Isolation: multiple transactions can occurr at the same time but are executed as they occurred sequencially.

If 2 concurrent transactions on the same table occurr, one execute and the other wait until the 1st ends.

➤ Durability: the effect of a transaction is permenent. Database index.

An index is an additional data structure in the database that is optimized for fast searching on a specific attribute in a table.

This data structure stores the attribute entries in sorted order, pointing them to the corresponding row in the original table. Since entries are sorted you can execute a query on them in O(logN) or O(1) instead than in O(N).

The trade off are that:

- the additional data structure take up more space
- every write operation is a bit slower because also the index need to be updated

When to chose a relational DB

First when you need to execute very powerful queries to retrieve data (i.e. multi-rows SQL transactions).

Non relational DB have their own query language, but this not always support complicated types of queries like SQL. Second when you need strong consistency on your data.

For example, when you make an update in the DB you want to immediately see these updates reflected everywhere.

Non relational DB are usually not fully ACID compliant and guarantee only eventual consistency.
