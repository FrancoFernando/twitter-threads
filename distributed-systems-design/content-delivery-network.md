https://twitter.com/Franc0Fernand0/status/1540698393454018562?s=20&t=_oMjO2AzWDWRATgxEOI9hw

Content Delivery Networks (CDNs) deliver a large portion of the internet content.

They have 2 main benefits:

1. cache web content closer to the users

2. create a low latency overlay network connecting clients and origin servers

But how CDNs guarantee this?

//Thread// ↓



Working principle

At high level a CDN works like a cache.

When a CDN server receives a request, it checks if the requested resource is cached locally.

If not the server fetches the resource from the origin server, cache it and return it to the client. Geographical distribution

If the client is located far from a server, the latency will be high regardless how fast the server is.

This is why CDN servers are placed in multiple geographical places to be close to the clients. CDN clusters localization

How do clients know which cluster of CDN servers is the closest to them?

The answer is usually using a global DNS load balancing. Global DNS load balancing

It is an extension of DNS capable to infer the clients location from their IP address.

Knowning this, the global DNS returns a list of geographically close clusters.

The list is usually sorted considering network congestion and cluster health. Overlay Network

The main benefit of a CDN is not its caching capabilities, but its underlying network.

Differently from CDNs, the public internet has not be designed for performance.

Its routing protocol evaluates network paths without considering congestion and latencies. Network optimization

The routing algorithms of CDNs use special techniques to select network paths with low congestion and latency.

As an example they use TCP optimizations and updated data about the health of the underling network. Network optimization-2

As a further optimization, CDN are also placed at the exchange points where ISP are connected.

This allows to run the communication between a client and the origin server almost always over network links belonging to the CDN. Caching

A CDN has usually multiple content caching layers.

The top layer is made of edge server clusters placed at different geographical locations.

The other layers are made of intermediate server clusters placed at a reduced number of locations. Why this layering structure?

Having a high number of edge clusters allows to serve geographically dispersed clients.

But as a downside, it reduces the cache hit ratio.

The intermediate layers cache a large fraction of the content reduce the load on the origin server. Additional reading

For a more detailed explanation about how CDNs works, I strongly suggest this great thread by @alexxubyte

https://twitter.com/Franc0Fernand0/status/1540698436600680453?s=20&t=_oMjO2AzWDWRATgxEOI9hw

