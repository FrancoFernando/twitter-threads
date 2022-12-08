Microservices are not necessarily better than monoliths.

Using microservices can be a good choice or not depending on the specific use case.

The 6 main factors to take into account: ↓

Coupling

Microservices can be a reasonable choice only when they are loosely coupled.

Otherwise they end up being ugly not mantainable distributed monoliths.

Common reasons of coupling are poor APIs or libraries that need to be updated in lock step to multiple services. Technology stack

In theory each microservice can use a different tech stack, but this has some cons.

First, having different tech stacks can be an obstacle for developers to change team.

Second, providing cross service functionalities and libraries can be more difficult. Remote communication

Microservices usually mean having more distributed processes communicating over the network.

But this is a problem also monoliths need to deal with at a smaller scale.

Indeed they also serves external requests or can depend on external APIs. Testing

Testing single microservices is not more difficult than testing monoliths.

What's harder is testing the integration of all the microservices.

Sometimes weird and unexpected behaviours emerge only when microservices interact together in production. Data consistency

With microservices the data are usually splitted in multiple data stores.

Ensuring strong data consistency in such scenario is hard, expensive and can slow down the system.

This is why often microservices only guarantee eventual consistency. Operability

Monitoring performances degradation and debugging failures is more challenging with microservices.

This is why it is very important having a good observability platform.

It's also useful having a common way for each microservice to deploy to production.
