There are 3 main categories of load balancers:

- DNS based
- transport layer (L4)
- application layer (L7)

This how they work and their differences: {1/12} ↓

Load balancers are a fundamental part of every distributed architecture.

They essentially balance the clients requests between a pool of servers.

But they can have more functionalities according to their category.

{2/12}

1. DNS load balancers

The idea is to add the public ip address of the servers to the application's DNS record.

The clients can than pick up one of the addresses during the DNS resolution process.

Usually the choose of the address is made using a round robin strategy.

{3/12}

This is probably the simplest way of implementing a load balancer, but it has some drawbacks.

The main one is that it's not resilient to failures.

If one of the servers gets unavailable, the DNS server continue to provide its IP address.

{4/12}

Even removing the IP address of the failed server from the DNS record won't be effective.

The change needs time to propagate since the DNS entries are usually cached.

This is why DNS load balancing is mostly used in practice to distribute traffic among data centers.

{5/12}

2. Tranport layer load balancers (L4)

These load balancers work at TCP level of the network stack.

The idea is to map physical network cards to multiple virtual ip addresses.

Each virtual ip address (VIP) is associated to a pool of servers.

{6/12}

When a client establishes a TCP connection to a VIP, the load balancer picks a server from the pool.

All the traffic between the client and the server flows through that connection.

The load balancer takes care of translating the VIPs to the servers's addresses.

{7/12}

The advantages of using a L4 load balancer are that it is fast and very flexible.

The drawback is that can only redirect bytes without knowing their actual meaning.

So it can't support high level features like terminating TLS connections.

{8/12}

3. Application level load balancer (L7)

These load balancers act as HTTP reverse proxies.

They check HTTP requests received from a client and send them to a server picked from a pool.

They handle 2 TCP connections, one with the client and another with the server.

{9/12}

L7 load balancers are powerful and can do many things like:

- demultiplex HTTP requests sharing the same TCP connection

- rate limiting request according to the HTTP header

- route HTTP requests belonging to a logical session to the same server using cookies

{10/12}

Their main drawback is that they have lower throughput respect to L4 load balancers.

This makes them more vulnerable to DDOS attack.

Moreover all the traffic direct to an application goes through the load balancer, making it potentially a single point of failure. 

{11/12}

A last side note. These categories of load balancers are not mutually exclusive.

It's not uncommon to see companies using both L4 and L7 load balancers.

Usually the L4 load balancers are placed before the L7 load balancers.

{12/12}







