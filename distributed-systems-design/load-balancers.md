https://twitter.com/Franc0Fernand0/status/1443869983457615874?s=20&t=kObvIjelj9qDiu4mJE-FGg


They are used in almost every large scale system.

Keep reading to know what they are and understand how they works.

A thread.



Introduction

Let's start with a simple use case.

A client issues requests to server.

The server performs some business logic and fetch some data from a database.

The server returns responses to the client.

All fine, but what happens if the system becomes bigger? Let's say we have now n clients issuing multiple requests .

The server has limited resources and throughput.

The more requests the server receives the more it get overloaded.

The system becomes soon very slow or even worst a failure happens.

How can we prevent this? Scaling the system

There are 2 possibilities:

🔸 vertical scaling, increasing the power of server.
🔸 horizontal scaling, adding more servers.

The problem of vertical scaling is that it is limited by the maximum amount of resources a single server can have. At a certain point we need to scale horizontally.

Teoretically, if we add m servers having the same resources, the system can handle m times the initial load.

But this is true only if the requests of the client are equally distributed across the servers. How do we equally distribute the requests of the clients across the servers?

And how does each client know to which server direct its requests?

Load balancers are the answer. Definition

A load balancer is a server sitting between a set of clients and a set of servers and performing the job of balancing the clients requests between the servers.

A LB acts as reverse proxy, redirecting and distributing the requests from the clients to the servers.



Load balancers can be placed not only between clients and servers, but in many other different places of the system like:

🔸 between servers and databases
🔸 at DNS layer when dealing with web servers



There are different types of load balancers and multiple way to categorize them.

A first way distinguishes between hardware and software load balancers.

A second way distinguishes between Layer 4 and Layer 7 load balancers, according to the network layer they act. Hardware LB

They are high-performance devices able to process high traffic from many kind of applications.

They can have the capabilities to support virtual LB instances on the same hardware.

They are efficient, but also expensive.

Popular vendors are Citrix or Radware. Software LB

They are sw applications that can fully replace hardware LB while delivering analogous functionalities and superior flexibility.

They allows to save space and reduce hardware costs.

Popular LB are Nginx, HAProxy, AVI Vantage. Layer 4 and 7 LB

Layer 4 LB: redirect traffic based on the TCP or UDP ports of the packets along with their source and destination IP addresses.

Layer 7 LB: redirect traffic inspecting the actual content of each packet, including HTTP headers and SSL session IDs. How the LB knows to which servers distribute the traffic?

The system administrators can configure LB and servers to know about each others.

When they add/remove a new server, this is register/deregister it with the LB. How LB distribute the requests to the servers?

There are many different server selection strategies.

Let's revise the most popular ones. Random redirection

The LB redirects the traffic to the servers following a pure random order.

This strategy could have problem because a server can get overloaded by chance. Round Robin

The LB evenly redirects the traffic to the servers following a certain circular order.

A variant is the weighted RR where each server receives a number of requests according to a given weight.

This is useful if some servers are more powerful than others. Performances based redirection

This is a more involved approach.

The LB performs healthy checks on the servers to get statistics like:

🔸how much traffic they are handling any given time
🔸how long they take to answer
🔸how many resourcers they are using

👇

The LB redirects the traffic according to this information.

If the LB gets to know that a server is doing poorly, it stops redirecting request to that server.

Instead if the LB notices that a server is not overloaded and performs well, it redirects more traffic to it. IP based redirection

The LB calculates a hash of the client's IP address and redirects the traffic according to the value of the hash.

This can be useful if the server caches the results of the requests.

Why? 👇

All the requests of the same client are always redirected to the same server in which the responses of the particular client has been cached.

So cache hits get maximized. Path based redirection

The LB distributes requests according to their URL.

Why can be useful?

All the requests for a service are redirected to a specific set of servers.

This separates the services making easier the deployment and isolating them in case of failures. Which strategy is better?

No one.

Each strategy has pro and cons and it's always wise to select the best strategy fitting your use case.

In absence of clear requirements, Round Robin is always a good strategy to start with. It can also make sense to have multiple layers of LB adopting different strategies.

The LB in the first layer redirects the traffic to the LB in the second one that then redirects the traffic to the servers.

For example the first layer could use the hash and second the RR. Redundant Load Balancers

LB can be single point of failures in a system.

If you have a single LB and this gets overloaded or fails, the whole system goes down.

The prevent this multiple replicas of the LB are usually connected into a cluster.



Each replica monitors the healthy of the others.

In case the main LB fails, another replica takes over and start rerouting the traffic. Advantages of introducing LB

🔸 Optimize the use of resources distributing clients requests across servers

🔸 Improve the user experience ensuring a faster response time

🔸 Prevent system downtime rerouting requests from overloaded/failed servers to healthy ones

👇

🔸 Give more flexibility in adding/removing servers and performing server maintenance

🔸 Introduce more redundancy and resilience into the system

Clustering

Load balancing shares common traits with clustering but there is a main difference.

Servers in a cluster are aware of each other and work toward common purpose.

Load balanced servers just react to commands from LB and don't know about each other.
