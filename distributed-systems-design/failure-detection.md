Failure detection is one of the most complex topics in distributed systems.

Many things can go wrong when a client sends a request to a server.

So how to be sure that a server is really dead?

//Thread// ↓

{1/10}



Let's suppose that a client sends a request to a server and don’t get any response.

This doesn't necessarily mean that the server is dead.

Many things may have happened:

a) the request got lost and the server didn’t receive it

{2/10} b) the server is very slow and the response will be delivered later

c) the server temporarily stopped responding (e.g. during garbage collection)

d) the server crashed

e) the response got lost

f) the request/response is waiting in a queue

{3/10}

What could a client do in this case ?

A 1st possibility is setting a timeout triggered if a response is not received within a certain time.

If the timeout is triggered, the server is considered not available.

Then the client either throw an error or retry the request.

{4/10}

It's important to set the timeout carefully.

If it's too short the client could wrongly assume that the server is unavailable.

If it's too long the client could waste time waiting a response.

The right timeout is depend on the application logic and the use cases.

{5/10}

A 2nd possibility is that the client proactively mantains a list of available servers.

There are 2 ways:

a) pings: periodic requests sent to the server to check if it's available

b) hearthbeats: periodic messages sent by the server to confirm its availability

{6/10}

If a response to a ping or hearthbeat is not received within a given timeframe, the server is considered unavailable.

Both approaches are valid, but the 2nd should be preferred when an action need to be taken as soon as the server is unavailable.

{7/10}

For example load balancers use both passive and active health checks.

Passive health checks are used while routing requests to the servers.

If a server is not reachable or it returns a non retriable status code, the load balancer take the server out of the pool.

{8/10}

Active health checks require instead explicit support from the servers that expose a dedicated health endpoint.

The load balancer queries periodically the endpoint to understand the server's health.

The endpoint could be implemented in different ways.

{9/10}

In its simplest form it could always return an OK response since most of the requests will timeout if the server is degraded.

Otherwise the endpoint could use metrics like available memory, CPU usage or number of concurrent requests to decide if the server is degraded.

{10/10}
