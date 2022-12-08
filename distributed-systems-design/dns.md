https://twitter.com/Franc0Fernand0/status/1528012705352896512?s=20&t=6dU-uE_Tuf7se1a62DaVhA

DNS is the protocol converting human readable website names into IP addresses.

It's not only the phone book for the internet.

But also an example of key-value store that is:

1. distributed
2. hierarchical
3. eventually consistent

How DNS works ?

[Thread] ↓



Let's consider the scenario where a browser try to access a website.

In this case the browser represents a DNS client.

How the browser get the address of www. mywebsite. com ? The browser checks its local cache to see if it has already the corresponding IP address.

If the IP address isn't cached, it sends a DNS request to the DNS resolver.

This is a dedicated server usually hosted by an Internet Service Provider (ISP). The DNS resolver checks its local cache.

If the corresponding IP address isn't cached, it tries to iteratively solve the request.

Iteratively means that it tries to contact different other servers until it doesn't get the IP address. First the DNS resolver sends a request to a root name server.

This is a server mapping the top level domain ".com" to the address of the name server responsible for that domain.

The address of the ".com" name server is sent back to the DNS resolver. The DNS resolver sends a resolution request for "mywebsite .com" to the ".com" name server.

The ".com" name server maps "mywebsite .com" to the address of the authoritative name server responsible for it.

This address is sent back to the DNS resolver. The DNS resolver sends a resolution request for "www. mywebsite .com" to the authoritative name server.

The authoritative name server then return the destination IP address.

But what if the request included a subdomain ? In that case, the authoritative name server would have returned of the server responsible for the subdomain.

And an additional request by the DNS resolver would be required. The whole resolution process is time consuming and requires many round trip.

This is why caching is extensively used by all the components.

It's important to properly set the expiration time of those cache entries.

This time is commonly called time to live (TTL). As usual there is a trade-off.

If the TTL is too high, clients won't be able to see a change for a long time.

If the TTL is too low, the load on name servers increase and as well the average response time.
