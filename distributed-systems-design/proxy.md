https://twitter.com/Franc0Fernand0/status/1436317214722961420?s=20&t=kObvIjelj9qDiu4mJE-FGg

🔥 ALL what YOU need to know about PROXIES 🔥

Proxies are a fundamental component of almost every distributed system.

You should understand:

🔸 what proxies are
🔸 which are the different kind of proxies
🔸 why they are so useful.

Do you want more?

Keep reading 🧵 👇



Let's start with a general definition.

In real life a proxy is a person who is given the power or authority to do something for someone else.

For example, if you are not available to vote, you can nominate another person to act as your proxy and vote for you. In distributed systems, a proxy is a server acting as intermediary between a set of clients and a set of servers.

We can distinguish 2 categories of proxies:

🔸 forward proxy: the proxy acts on behalf of the clients
🔸 reverse proxy: the proxy acts on behalf of the servers

A (forward) proxy is a server that acts on behalf of the client.

If the proxy has been configured correctly, when a client want to communicate with a server the requests from the client don't go directly to the server but to the proxy.

The next steps are quite obvious 👇



The proxy then

🔸 forward the requests to the proper server
🔸 wait for responses
🔸 send the responses back to the corresponding client. Notice how in this way the server doesn't know who is the client.

It only knows the source IP address of the proxy and not of the client.

So a forward proxy can secure and hide the identity of the client.

This is basically the same principle how VPNs work. What are the main advantages of using forward proxies?

🔸 clients can access servers that they would not be supposed to access otherwise
🔸 the proxy can be used to selectively send/block requests
🔸 the proxy can log or monitor requests
🔸 the proxy can cache responses

A reverse proxy is a server that acts on behalf of another server.

If the reverse proxy has been configured correctly, the requests of the client are not received directly by the server, but by the reverse proxy.

Once again, the next steps are quite obvious 👇



The reverse proxy then

🔸 forward the requests to the proper server
🔸 wait for responses
🔸 send the responses back to the corresponding client. Notice how the client has no idea that it is communicating with the reverse proxy.

The responses are then returned to the client, appearing as if they were originated from the server itself.

So a reverse proxy can secure and hide the identity of the server. An example.

Suppose to type in your browser.

Your browser makes a DNS query to get the IP address of my website.

If my website used a reverse proxy, the DNS would return the reverse proxy IP address instead that the one of my website. (francofernando.com) What are the main advantages of using reverse proxies?

🔸 Security and anonymity
🔸 Performance
🔸 Load balancing

Let's check them in details 👇

Security

By intercepting requests directed to the backend servers, a reverse proxy can not only protect their identities but can also act as an additional defense against security attacks. Performance

Reverse proxies can cache static content reducing the overall system latency.

They can also take the load off of the servers performing additional tasks like:

🔸 Data compression / decompression
🔸 Data encryption / decryption
🔸 HTTP authentication

Load Balancing

Reverse proxies can distribute client requests across a group of servers in a way that:

🔸 maximizes speed and capacity utilization
🔸 ensures that no one server is overloaded

Introducing reverse proxies in a system have also disadvantages:

🔸 the system complexity increases
🔸 reverse proxies redundancy is necessary to avoid single points of failure

It is a matter of trade offs, deciding if use or not a reverse proxy layer in your system. Do you want some examples of reverse proxy implementation?

Check out these:

🔸 Nginx
🔸 Caddy
🔸 HAProxy
🔸 Squid

API Gateways

In microservices architectures, reverse proxies can also act as API Gateways.

An API gateway is a single entry point for external clients that implements an abstraction layer hiding all the details about microservices.

👇



The API gateway handles the requests from the clients in one of two ways:

🔸 routing the requests directly to the appropriate service.
🔸 fanning out the requests to multiple services and aggregating the results

Rather than provide a one-size-fits-all style API, the API gateway can also expose a different APIs for different clients.

It's not uncommon also to have different API gateways for web application, mobile application, and external 3rd party applications. API gateways provide many benefits:

🔸 reduce the volume of requests and traffic, combining multiple API calls
🔸 allow a flexible implementation of internal microservices, decoupling them from the clients
🔸 make easier collect log, metrics and monitoring the activities

API gateways have also some drawbacks:

🔸 the complexity increase since there is another component that must be developed, deployed and managed
🔸 an additional network hop through the API gateway is introduced

Notice how forward and reverse proxies have an exact opposite interaction pattern.

Forward proxies send out requests on behalf of the client and receive responses from the server.

Reverse proxies receive requests on behalf of the server and send out responses to the client.

