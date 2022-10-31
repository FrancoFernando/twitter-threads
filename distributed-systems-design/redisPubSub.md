Redis is commonly known as a key-value server, but actually is also a messaging server.

This is how Redis Pub/Sub works and when it's a good choice: {1/10} ↓

Redis Pub/Sub uses a data type called channel to support publish and subscribe operations.

A client can subscribe to multiple channels and a channel can have 0 or multiple subscribers.

When new content is published on a channel, Redis push it out to the subscribers.

{2/10}

Publishers and subscribers are loosely coupled because they interact only through channels. 

Redis uses an at-most-once delivery semantic to send messages to the subscribers.

This means that only (and all) currently connected subscribers get the messages.

{3/10}

Once a message is delivered to all subscribers, it is deleted from the channel.

So the data going through a channel is stateless and is simply dropped if there are 0 subscribers.

Disconnected subscribers or later subscribers won't get any copy of past messages.

{4/10}

Redis keep track of channels and subscribers using hash tables as underlying data structures.

A 1st hash table with chaining collision handling is used to map channels to subscribers.

Subscribers are here stored using a linked list for fast iteration during a publish.

{5/10}

A 2nd hash table is used as a set to store all the channels subscribed by a client.

Here the choice of a hash table over a linked list allow fast retrieval for subscribe and unsubscribe operations.

Clearly the 2 hash tables are kept in synch.

{6/10}

Publishing a message requires:

- hashing the channel name to get a hash chain 
- Iterate the chain in case of conflicts
- Iterate the linked list of subscribers sending the message

{7/10}

Subscribe a channel requires:

- find the proper linked list as before
- append the subscriber to the list
- add the channel to the subscriber's hash table.

Unsubscribe a channel is similar but more expensive since removing a subscriber requires to scan the whole list.

{8/10}

Redis Pub/Sub is an efficient way to distribute messages, but it's important to know its pitfalls and strengths.

 These are its most appropriate use cases:

1. Real-time, low-latency messaging where messages are are only relevant to subscribers for a short time

{9/10}

2. Unreliable delivery messaging where messages lost is not critical

3. Cases where the number of subscribers and patterns per channel is relatively small

4. Subscribers require at-most-once delivery because target systems can't detect duplicates or are not idempotent

{10/10}

