TLS is a widely used protocol enabling secure communication at application level.

For example, HTTPS runs on top of TLS to provide:

1. encryption
2. authentication
3. security

But how TLS works?

//thread//



Encryption

• It guarantees that data can be read only by the 2 communicating processes

• Asymmetric encryption is used to generate an encryption key shared by the processes

• Symmetric encryption is then used to encrypt the data

• The reason of this is that asymmetric encryption is slower and more expensive than symmetric one

• The shared encryption key is periodically renegotiated by the 2 processes

• This minimize the data that can be deciphered if the key is broken

Authentication

• It allows the communicating parts to verify that the other is who it claims to be

• It's implemented with digital signature based on asymmetric cryptography

• Process A generates a pair of public-private keys, sharing the public with process B

• A signs all messages to B with the private key

• B verifies that the messages with from A using the pblic key

• B verifies the ownership of the public key shared by A with a certificate

• The certificate is verified by B before establishing the TLS connection

Integrity

• It ensure that the exchanged data is not tampered

• It's implemented with a message authentication code (HMAC)

• The sender creates a digest and include it in the message

• The receiver recompute the digest checking that's equal to the one in the message

Handshake

A TLS connection requires an handshake procedure between the 2 parties to:

• agree on a cipher suite to use (i.e. /HMAC and key exchange algorithms)

• define the shared public key used for symmetric encryption

• verify the certificates

The handshake can look an expensive procedure.

But it takes only 2 round trips with TLS version 1.2 and 1 with TLS 1.3.

Neverthless creating a connection has always a cost, so it's always good practice

• put servers close to the clients
• reuse connections when possible

HTTPS

For additional details about HTTPS, check out also this nice thread by @alexxubyte
