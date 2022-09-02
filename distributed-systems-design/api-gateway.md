An API Gateway is a reverse proxy acting as entry point in microservices architectures.

Some responsabilities of API gateways are:

- routing requests
- combine multiple APIs
- expose customized APIs

How do API Gateways accomplish this ?

//Thread// {0/9} ↓



An API Gateway is essentially a reverse proxy.

It acts as intermediary between clients and servers on behalf of the servers.

All the clients requests are received by the Gateway and not by the servers.

But the client doesn't know that it communicates with the Gateway.

{1/9}

The first task of an API Gateway is routing requests to the internal services.

Usually it uses a routing table mapping public APIs to internal APIs.

This allows internal APIs to change without breaking external clients.

{2/9}

In microservice architectures a public API can require stitching data from multiple services.

So another task of an API Gateway is querying those services and compose a response.

This relieves clients from knowing services to query and reduce their traffic voumes.

{3/9}

Anyway, composing APIs is not trivial.

First the Gateway needs to deal with possible data inconsistency between the different services.

Second the availability of composed API corresponds to the product of the involved services's availabilities, so it decreases.

{4/9}

Different clients (e.g. desktop vs mobile apps) can have conflicting requirements.

An API Gateway can expose customized APIs to meet the use cases of different clients.

Those APIs are then translated to internal calls.

{5/9}

Graph-based APIs like GraphQL are a commonly used technology to define customized APIs.

They expose a schema that describes the data and the clients can use it to precisely query the data they need.

The API Gateway translate thise queries into internal API calls.

{6/9}

API Gateways are usually responsible also for cross cutting functionalities like authentication.

A Gateway authenticates each external requests ensuring a client is who it says it is.

Once a request has been authenticated, the Gateway associate to it a security token.

{7/9}

Request plus token are then passed downstream to the internal services.

A token can contain every necessary information or be
opaque and require an external authentication service.

As alternative authentication mechanism, Gateways can also support API keys.

{8/9}

We discussed many benefits of using an API Gateway, but they have also some drawbacks:

1. it's an additional service to be mantained

2. if internal APIs change also the Gateway needs an update

But if there are many APIs and services, the benefits outweights to cons.

{9/9}
