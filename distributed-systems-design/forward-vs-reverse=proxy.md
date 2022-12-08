https://twitter.com/Franc0Fernand0/status/1517867427333390339?s=20&t=6dU-uE_Tuf7se1a62DaVhA

Proxies are servers acting as intermediary between a set of clients and a set of servers.

But which is the difference between forward and reverse proxies ?

[Thread] ↓



A forward proxy is a server acting on behalf of a client.

If the proxy has been configured correctly, the client's requests go to the proxy instead of the server.

The proxy:

1. forward the requests to the server
2. wait for responses sending them back to the client

In this way the server doesn't know who is the client.

It only knows the source IP address of the proxy.

So a forward proxy can secure and hide the identity of the client.

This is basically the same principle how VPNs work. The main advantages of using forward proxies are:

✓ clients can access servers they wouldn't be supposed to access
✓ the proxy can selectively send/block requests
✓ the proxy can log or monitor requests
✓ the proxy can cache responses

A reverse proxy is a server acting on behalf of another server.

If the proxy has been configured correctly, the client's requests are received by the proxy instead of the server.

The proxy:

1. forward the requests to the server
2. wait for responses sending them to the client

The client has no idea that it is communicating with the reverse proxy.

The responses are then returned to the client, appearing as if they were originated from the server itself.

So a reverse proxy can secure and hide the identity of the server. The main advantages of using reverse proxies are:

✓ Load balancing among group of servers
✓ Anonimity and increased security for the servers
✓ Better performances thanks to caching or to additional tasks executed in place of the servers

Introducing reverse proxies in a system has also disadvantages:

✗ the system complexity increases
✗ reverse proxies redundancy is necessary to avoid single points of failure

As usual it's a matter of trade offs deciding if using or not a reverse proxy layer in a system.
