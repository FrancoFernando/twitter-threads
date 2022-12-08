https://twitter.com/Franc0Fernand0/status/1525477042971623424?s=20&t=6dU-uE_Tuf7se1a62DaVhA

TCP is one of the most important network protocols.

It enables a reliable communication between 2 processes where data is transmitted:

1. in order
2. not corrupted
3. without duplication or gaps

But how does TCP work ?

[Thread] ↓

{1/9}



TCP divide a data stream of bytes into segments.

Segments have these properties:

1. sequencially numbered, so that the receiver can detect duplication or gaps

2. include a checksum used to check data corruption

3. need to be acknowledged by the receiver

{2/9}

Two processes need to set up a TCP connection before exchanging segments,

The connection is established through endpoints known as sockets.

A socket identify a process and the machine where it runs, tracking the connection state.

{3/9}

A TCP connection between 2 processes A and B is established with a 3-ways handshake:

1. A sends a SYN segment with a random number x

2. B sends a SYN/ACK segment with a random number y and x+1

3. A sends the first data with x+2 and y+1

{4/9}

Establishing a connection requires a full round-trip without application data exchange.

Same happens for closing a connection.

So it makes sense to keep a connection opened if it's likely another data exchange will follow.

Connection pools are usually used for this.

{5/9}

TCP not only implements a reliable communication channel.

It also put in place mechanism to avoid that:

1. the sender overwhelm the receiver
2. the underlying network get flooded

{6/9}

Flow control prevents the sender overwhelming the receiver.

The receiver store the segments in a dedicated buffer.

The buffer size is communicated to the sender with every acknowledge.

The sender use this info not to send segments not fitting into the buffer.

{7/9}

Congestion control prevents the network getting flooded.

The sender tracks the number of segments that can be sent without an ACK.

This number is known as congestion windows.

The window increases if segments ACK are received within a timeout, otherwise decreases.

{8/9}

It's clear that the smaller is the window, the less bandwith is used.

So the shorter is the round trip time, the sooner the window grows and the full bandwidth is used.

This is one of the reasons why it's so important having web servers close to the clients.

{9/9}
