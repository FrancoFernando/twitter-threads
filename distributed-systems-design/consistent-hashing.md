https://twitter.com/Franc0Fernand0/status/1606668322375962625?s=20&t=mRgJemXU58N1xIakXxwrLQ

Rendezvous hashing is a great way to implement hashing in distributed systems.

How it works and how it compares to consistent hashing:

{1/9} ↓

Hashing is commonly used in distributed systems to map keys to servers.

Keys are typically sharded data or cached client requests.

Ideally, the mapping has 2 properties:

• adding/removing a server is not expensive 

• keys are balanced in number between servers

{2/9}

The essential idea of rendezvous hashing is:

• calculate a ranking of all servers for each key

• map each key to the server with the highest ranking

• maintain the mapping above while adding and removing servers

{3/9}

A simple process is used to calculate the ranking:

• each key is hashed together with each server

• the server having the highest hash value is assigned to the key

{4/9}

Only the keys for which a server S has the highest ranking are remapped if S is added or removed.

If S is removed, the keys assigned to S are remapped to the server with 2nd highest ranking.

If S is added, the keys for which S has the highest ranking are remapped to S.

{5/9}

Typically, rendezvous hashing requires O(N) time to calculate the hash values for each key.

But there is a variant (the skeleton-based) that can achieve O(logN) time.

No additional space is required since each key's ranking is calculated on the fly.

{6/9}

It's interesting to compare the performances of rendezvous and consistent hashing.

Consistent has a query time of O(log(N)) for a key.

Rendezvous has a query time of O(N) that can reach O(log(N)).

N is larger for consistent hashing if it uses virtual nodes.

{7/9}

Consistent hashing requires memory to store hash values and mappings, while rendezvous does not.

Consistent hashing requires only a hash computation per key, while rendezvous requires N.

Rendezvous natively supports server replication without introducing virtual nodes.

{8/9}

All this makes rendezvous hashing a good candidate if:

• the cluster of servers is small

• the cluster is large but the memory footprint needs to be low

{9/9}




