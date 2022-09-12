HTTP is a widely used application level protocol based on a request response paradigma.

It's main use is to encode and transport information between a client and a server.

How does HTTP works in details ?

//Thread// ↓



Introduction

A typical HTTP transaction is made of 2 steps:

- a client sends a request message to a server

- the server replies with a response message

Here a message is a block of text composed by multiple fields. Messages

The main fields of a HTTP message are:

- the start line, indicating what a request is for or if the request was succesful

- the headers, composed by key-value pairs metadata describing the message

- the (optional) body containing the data

Requests

A HTTP server hosts resources like documents, images or collections of other resources.

HTTP requests allow to Create, Read, Update or Delete these resources.

Each request is stateless and contains all the necessary information to process it. Request methods

The requested CRUD operation is specified in the start line of the message by a request method.

The most commonly used methods are:

- GET: retrieve a resource
- PUT: update a resource
- POST: create a resource returning its URL
- DELETE: remove a resource

Properties

A request method can have 2 important properties:

- safety: the method have no side effects and can be cached. GET is safe, PUT, POST, DELETE no

- idempotency: the method can execute multiple times with the same result. GET, PUT, DELETE are idempotent, POST no

Responses

HTTP responses contain a status code informing the clients if their requests succedeed or not.

There are different code ranges:

- 200-299 indicate success
- 300-399 communicate a redirection
- 400-499 communicate client errors
- 500-599 indicate client errors

Transport layer

HTTP needs a transport layer protocol ensuring a reliable and secure communication channel.

Usually this protocol was TCP, but the latest HTTP version uses its own UDP based transport protocol.

When HTTP run on top of TLS, it's referred as HTTPS. Versions

HTTP has multiple versions like:

- 1.1 a TCP connection can be used for multiple transactions, but those need to be serialized

- 2.0 multiple transactions can be multiplexed on a TCP connection

- 3.0 an UDP transport protocol further optimizes the communication
