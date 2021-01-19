This archive is based on: https://searchsecurity.techtarget.com/definition/Secure-Sockets-Layer-SSL

--------
SSL:

Secure Socket Layer (SSL) is a networking protocol designed for securing "connections" between web clients and web servers over an insure network (i.e., Internet).

After being formally introduced in 1995, SSL made it possible for a web server to securely enable online transactions between consumers and businesses. Due to numerous protocol and implementation flaws and vulnerabilities, SSL was deprecated for use on the Internet by the Internet Engineering Task Force (IETF) in 2015 and has been replaced by the Transport Layer Security (TLS) protocol.

----
While TLS and SSL are not interoperable, versions of TLS through 1.2 were backward-compatible with SSL 3.0.

However, backward compatibility with SSL was removed from TLS 1.3, the current version of TLS that was published in 2018.

----
SSL was originally specified in the 1990s as a proprietary (ownership) protocol that enabled "Netscape browser clients" using HTTP to communicate securely with "Netscape web servers".

While version 1.0 of SSL was never released, version 2.0 of the protocol made its debut in 1995. SSL was the first widely used protocol for securing online transactions, and it eventually came to be used to secure "authentication" and "encryption" for other applications at the network transport layer.

----
SSL uses a combination of "public key encryption", and "private key encryption", and other cryptographic functions to secure a connection between two machines.

Typically, a "web server" or "mail server" and a "client system", communicating over the Internet or other TCP/IP network.

    - SSL provides a mechanism for encrypting and authenticating data sent between processes running on a client and server;
    - SSL as well as mediating the secure exchange of private keys for session encryption, through the use of an SSL certificate issued by a trusted CA.

----
SSL runs above the transport layer (TCP) and the network layer (IP), which are responsible for the transport of data between processes, and the routing of netowrk traffic over a network between client and server, respectively.

SSL runs below application layer protocols, such as HTTP and SMTP (Simple Mail Transport Protocol.

The "sockets" parts of the term (SSL) refers to the "sockets" method of passing data between a client and a server program in a network, or between processes in the same computer.

----
The TLS protocol evolved from SSL, and has officially superseded it. Although the terms "SSL" or "SSL/TLS" are still commonly used to refer to the protocol used to secure Web/Internet traffic.

SSL/TLS is the most widely deployed security protocol used today, and according to Google, it is being used to secure more than 50% of the pages loaded by the Chrome browser.

In addition to supporting the transmission of web pages, SSL has been implemented for applications, such as:
    - E-mail;
    - File transfer;
    - Instant messaging (IM);
    - Voice over IP (VoIP).


--------
Importance of SSL:

SSL is historically important because it was the first widely used and broadly implemented network protocol to enable cryptographically secured communications between previously unconnected client and server systems.

While SSL began as a proprietary protocol designed and implemented by Netscape, the web server software company published its protocol and made it available for implementation by other companies. By making the protocol accessible to its competitors, Netscape was able to gain web server market share with its secure web server product, while, at the same time, ensuring that the SSL protocol would become an IETF proposed standard.

SSL is still implemented, mostly in legacy systems. But in most cases, it should be replaced with TLS for improved security, and to avoid vulnerabilities in and exploites of the older protocol.

----
While the protocol itself is obsolete, SSL persists in many places as a way to described either TLS or SSL being used to secure transport layer communications.

For example, CAs often market their website certificates as "SSL certificates", because that is the term more familiar to their cunstomers.


--------
How SSL works:

The SSL protocol includes two subprotocols:
    - The Handshake Protocol;
    - The Record Protocol.

----
The "handshake" protocol defines how a web client and a web server establish an SSL connection.

Including the negotiation of which cryptographic systems each host is willing or unwilling to use for communication.

----
The "record" protocol defines how communicating hosts exchange data uaing SSL.

Including specificarions for how data is to be prepared for transmission, and how it is to be verified or decrypted on receipt.

----
SSL also specifics processes for exchanging cryptographic material, such as:
    - SSL certificates for authenticating web servers;
    - Public keys for authentication of transmitted data;
    - Private keys for session encryption.

----
As part of the initial "handshake" process, a server presents its "SSL certificate" to authenticate itself to the client. Server certificates follow the X.509 certificate format defined by PKCS (Public Key Cryptography Standards).

The authentication process uses "public key encryption" to validate the digital certificate, and to comfirm that a server is, in fact, the server it claims to be.

SSL certificates, like any digital certificate, should be issued by a trusted CA.

----
Once the server has been authenticated, the client and server established "cipher settings" and a "shared key" to encrypt the information they exchange during the remainder of the session.

This provides data confidentiality and integrity.

This whole process is invisible to the user. For example, if a Webpage requires an SSL connection, the URL will change from HTTP to HTTPS, and a padlock icon will appear in the browser once the server has been authenticated.

----
The "handshake" also allows the client to authenticate itself to the server.

In this case, after "server authentication" is complete, the client must present its certificate to the server to authenticate the client's identity, before the encrypted SSL session can be established.


--------
Difference between SSL and TLS:

After the IETF officially took over the SSL protocol to standardize it through an open process, version 3.1 of SSL was released as TLS 1.0. The name was changed to avoid potential legal issues with Netscape.

Many attacks against SSL have focused on SSL implementation issues. But the POODLE (Padding Oracle On Downgraded Legacy Encryption) vulnerability is a known flaw in the SSL 3.0 protocol itself. Exploiting the way in which it ignores padding bytes when running in CBC (Cipher Block Chaining) mode. This flaw allows an attacker to decrypt sensitive information, such as authentication cookies.

TLS 1.0 (SSL 3.1) is nor vulnerable to this attack, because it specifies that all padding bytes must have the same value and must be verified.

----
Other key differences between SSL and TLS that make TLS a more secure and efficient protocol are:
    - Message Authentication;
    - Key material generation;
    - Supported cipher suits with TLS supporting newer and more secure algorithms.

----
TLS 1.3 is the most recent version published in 2018.



========
[web link: https://searchsecurity.techtarget.com/definition/Transport-Layer-Security-TLS]

TLS:

Transport Layer Security (TLS) is a protocol that provides authentication, privacy, and data integrity between two communicating computer applications. It is most widely-developed security protocol used today, and os used for Web browser and other applications, that require data to be securely exchanged over a network, such as:
    - Web browsing sessions;
    - File transfers;
    - VPN connections;
    - Remote desktop sessionss;
    - Voice over IP (VoIP).

--------
History and development:

The Internet Engineering Task Force (IETF) officially took over the SSL protocol to standardize it with an open process and released version 3.1 of SSL in 1999 as TLS 1.0. The protocol was renamed TLS to avoid legal issues with Netscape, which developed the SSL protocol as a key feature part of its original Web browser.

According to the protocol specification, TLS is composed of two layers:
    - the TLS "record" protocol;
    - the TLS "handshake" protocol.

The "record" protocol provides connection security.

The "handshake" protocol allows the server and client to authenticate each other, and to negotiate encryption algorithms and cryptographic keys, before any data (a secret key) id exchanged.


--------
TLS attacks:

Implementation flaws have always been a big problem with encryption technologies, and TLS is no exception.

The infamous "Heartbleed" bug was the result of a suprisingly small bug in a piece of logic that related to OpenSSL's implementation of the TLS "heartbeat" machanism.

TLS "heartbeat" machanism is designed to keep connections alive, even when no data is being transmitted.

----
Although TLS is not vulnerable to the "POODLE" attack, a variant of the attack has exploited certain implementation of the TLS protocol that don't correctly validate encryption padding byte requirements.


--------
TLS 1.3 security enhancements:

Finalized in 2018, TLS 1.3 is the current version of the protocol.

    - TLS 1.3 was developed to address various vulnerabilities that have beed exposed over the past few years;
    - TLS 1.3 was developed to reduce the chance of implementation errors;
    - TLS 1.3 was developed to remove features no longer needed.

----
For example:
    - MD5 cryptographic hashes are no longer supported;
    - PFC (Perfect Forward Secrecy) is required;
    - RC4 negotiation is prohibited (forbidden).

----
All known vulnerabilities against prior versions of TLS, such as:
    - BEAST;
    - CRIME;
    - Protocol Downgrade Attacks;
have also been eliminated.

----
Popular Web browsers, such as:
    - Google Chrome;
    - Mozilla Firefox;
use TLS 1.3 by default, where possible.

In 2018, the Payment Card Industry Data Security Standard mandated (required) the use of TLS 1.1 or higher in most situations.

----
In addition to its enhanced resilience, TLS 1.3 is faster due to a "more efficient handshake" between the two systems communicating.



========
[web link: https://searchsecurity.techtarget.com/tip/SSL-certificate-best-practices-for-2020-and-beyond]

SSL certificate best practices for 2020 and beyond:

SSL/TLS security is continuously improving, and there are steps site owners should take to ensure the safety of their SSL certificates, websites and users.

Read on to learn more...






<EOF>
