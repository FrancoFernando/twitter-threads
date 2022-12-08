https://twitter.com/Franc0Fernand0/status/1522940457742970886?s=20&t=6dU-uE_Tuf7se1a62DaVhA

Load balancers are servers sitting between a set of clients and a set of servers.

They act as reverse proxies, redirecting and distributing the requests to the servers.

But how they distribute the requests ?

There are 6 main strategies to know.

[thread] ↓



Random redirection

The Load Balancer redirects the traffic to the servers following a pure random order.

This strategy could have problem because a server can get overloaded by chance. Round Robin

The Load Balancer evenly redirects the traffic to the servers following a certain circular order.

This is an easy to implement and simple strategy and it's a good starting point in many cases. Weighted Round Robin

A variant of the Round Robin where each server receives a number of requests according to a given weight.

This is useful if some servers are more powerful than others. Performances based

The Load Balancer performs healthy checks on the servers to get statistics.

It then uses these data to:

• stop redirecting requests to overloaded servers
• redirect more traffic to servers performing well

IP based

The Load Balancer calculates a hash of the client's IP address, redirecting the traffic according to this value.

The requests of a given client are always redirected to the same server.

This can be useful if the server caches the results of the request. Path based

The Load Balancer distributes requests according to their URL.

So the requests for a service are always redirected to the same servers.

This separates the services making easier the deployment and isolating them in case of failures. Which strategy is better? No one.

Each strategy has pros and cons and you should adopt the best strategy fitting your use case.

In absence of clear requirements, Round Robin is always a good strategy to start with. It can also make sense to have multiple layers of LB adopting different strategies.

For example the 1st layer could use the hash approach to redirect traffic to the 2nd layer.

The 2nd layer could then use Round Robin to redirect traffic to the servers.
