## Secure Channel

Secure Channel, also known as Schannel, is a set of security protocols that help
offer secure encrypted communications and authentication between a client and a
server

Schannel is a security package that uses the following four protocols on
Windows:

+ Transport Layer Security (TLS 1.1)
+ Transport Layer Security (TLS 1.2)
+ Secure Sockets Layer (SSL 3.0)
+ Secure Sockets Layer (2.0)

To create a Schannel connection, the clients and servers are both required to
obtain Schannel credentials and create a security session

Once the client and server connection is obtained, the security credentials
become available

If a connection is lost for any reason, the client and server can automatically
renegotiate the connection and finish all communications
