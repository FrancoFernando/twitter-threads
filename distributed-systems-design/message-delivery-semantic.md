Imagine Santa Claus asks you to run a service that brings gifts to families.

You want to deliver each gift correctly, but things like traffic or accidents could get in the way.

You can offer Santa Claus three options:

At least once delivery: if you don't receive a call from a family, you assume the gift wasn't delivered and send another. The bad thing is that you might give more gifts than necessary.

At-most-once delivery: you send a gift, but if something goes wrong, you don't redeliver it. The bad thing is that a family might not have a gift.

Exactly-once delivery: you promise that the gift will only come once, no more and no less. 

Distributed systems do not deliver presents but messages over a network.

Anyway, they work pretty much the same way.

The main difference is that they can only use the at-least-once and at-most-once deliveries.

The only way they can get an exactly-once semantic in practice is by simulating it in 2 possible ways:

- implement a deduplicating message logic on the receiver side

- using idempotent messages.
------------

Distributed systems works because nodes exchange messages over a network.

There are 3 kind of messages delivery semantics between 2 nodes: 

- exactly-once
- at-least-once
- at-most-once

But only the last 2 can be actually implemented. 

This is why ↓ {1/7}

Let's suppose that a node A sends a message to a node B. 

To be sure that the message has been received, node A needs to receive an acknowledge from B.

There are 2 different possibilities according to when the message is acked.

{2/7}

1. B acknowledges the message immediately before processing it.

A receives the ack and thinks that everything is fine.

But if B crashes during the processing, the message is lost forever.

So the message can be either received or not by B (at-most-once delivery).

{3/7}

Actually things are more complicated if there is a message queue in the middle and multiple workers. 

In this case the broker shall ensure that a message is not delivered to any other worker once it’s been acked. 

Kafka handle this coordination using ZooKeeper.

{4/7}

2. B acknowledges the message after it has been processed.

If B crashes before acking the message or the ack isn’t delivered for a network partition, A will redeliver it.

So the message can be either received once or multiple times by B (at-least-once).

{5/7}

Since these are the only 2 possibilities, it's not possible to  guarantee that a message is received exactly once.

The only way to get an exactly-once semantic in practice is by faking it in 2 possible ways.

The 1st is implementing a deduplicating message logic on B.

{6/7}

The 2nd one is using idempotent messages that can be applied more than once without side effects.

RabbitMQ attempts to guarantees an exactly once delivery using the above 2 techniques.

{7/7}

