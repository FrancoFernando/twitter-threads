Message queues are a core component of distributed systems.

Widely used implementations are: Amazon SQS, Kafka or AzureQueue storage.

What they are and which benefits they bring while designing a system:  {1/9} ↓

Message queues provide an asynchronous communication channel between 2 entities: producers and consumers.

Producers generate messages and put them in the queue.

Consumers retrieve the messages from the queue and process them

Such kind of channel is useful in many scenarios. 

For example, multimedia applications often need to process content for different user's needs.

So they upload the content to a file store and send a request to a processing service. 

{3/9}

Simply sending the request to the processing service wouldn't be a great idea.

Indeed the service could fail for any reason.

A message queue provides instead a more robust solution.

It can act as temporary buffer until the request isn't succesfully processed.

{4/9}

According to how a message is delivered, message queues provides 2 types of communication channels.

1. Publish-subscribe

They implement a broadcast communication style where each consumer instance receive a message copy.

Usually the messages are event notifications.

{5/9}

2. Point to point

They can implement two communication styles:

- one-way where a message is delivered to only one consumer that will eventually process it

- request-response where each producer has also a dedicated response channel from which it reads consumers replies

{6/9}

The use of message queues provide many benefits. Here I lists the main ones.

1. Robustness

The producer can send requests to the consumer even if this is temporarily unavailable.

{7/9}

2. Performances

The requests can be load balanced across multiple consumer instances, making the consumers side more scalable.

Moreover a consumer can read from the queue at its own pace. This smooths out load spikes, avoiding that consumers get overloaded.

{8/9}

3. Batch processing 

Message queues enables to process multiple messages in a single unit of work or batch.

Even if this increases the latency for the individual messages, it largely improves the overall throughput.

{9/9}
