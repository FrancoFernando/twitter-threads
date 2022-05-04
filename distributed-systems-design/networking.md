As a developer, is it important to have a basic understanding of how multiple machines communicate with each other.

This is a list of concepts concerning computer networking that you should be aware of.

A thread 🧵 👇



Communication Protocols

A protocol is a set of rules defining an agreement on how 2 parties should interact.

For network protocols the 2 parties are machines and the rules are the messages exchanged between these machines. Network Protocols

They defines the type, format, structure and order of the messages sent between 2 machines.

Messages are transmitted as sequences of bytes known as packets and divided in 2 parts:

- header: protocol related information
- payload: transmitted data

👇

There are many network protocols, grouped in layers according to their functionalities.

Here the most important layers together with the some relevant protocols for that layer:

- Application ➡️ HTTP
- Transport ➡️ TCP, UDP
- Network ➡️ IP

👇

Each layer is build on top of the previous one.

This means that the packet of a protocol belonging to a given layer (e.g. TCP) is encapsulated in the payload of a packet belonging to the lower layer (e.g. IP). IP Address

An address given to a machine connected to the internet network.

IPv4 addresses consists of 4 numbers separated by dots. All four numbers are between 0 and 255. Special addresses are:

- 127.0.0.1: your own machine
- 192.168.x.x: your private network

IP (Internet Protocol)

It is the protocol enableing machine to machine communication.

The smallest units of data exchanged between 2 machines are IP packets.

An IP packet contains:

- header: source/destination IP address, packet size
- payload: TCP or UDP packets

TCP (Transmission Control Protocol)

Create a connection between 2 machines enabling an ordered, reliable transmission of data between them.

To this purpose TCP exposes to the application protocols endpoints known as sockets.

👇

A socket is combination of an IP address and a port (a 16 bit number).

A pair of sockets uniquely identify a connection between 2 applications running on different machines.

A TCP packet contains:

- header: source/destination sockets
- payload: application protocol packet

HTTP (HyperText Tranfer Protocol)

It is the most famous application protocol and follows a request-response paradigm.

The client makes a request and the server issues a response including the requested content and relevant status information about the request. 

Computer networking is a huge topic and there are entire books dedicated to each one of the topics mentioned before.

The purpose of this thread was not to be exhaustive, but just to give you an idea of what is really important to know.
