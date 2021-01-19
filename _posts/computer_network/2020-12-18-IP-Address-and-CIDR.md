This archive is based on: https://searchwindevelopment.techtarget.com/definition/IP-address

--------
Internet Protocol Address:
This  definition is based on Internet Protocol Version 4 (IPv4).

See Internet Protocol Version 6 (IPv6) for a description of the newer 128-bit IP address. (IPV6 provides more IP addresses.)

----
Note that the system of IP address classes described here, while forming the basis for IP address assignment, is generally bypassed today by use of "Classless Inter-Domain Routing" (CIDR) addressing.

--------
In the most widely installed level of the Internet Protocol (IP) today, an IP address is a 32-bit number that identifies each Sender or Receiver of Information that is sent in Packets accross the Internet.

When you request an HTML page or send e-mail, the Internet Protocol (IP) part of TCP/IP includes your IP address in the message (actually in each of the packets if more than one is required), and sends it to the IP address that is obtained by looking up the Domain Name in the URL (Uniform Resource Locator) you request, or in the e-mail address you are sending a note to.

At the other end, the recipent can see the IP address of the Web Page requestor, or the e-mail sender. And the recipent can respond by sending another message using the IP address it received.

An IP address has two parts:
    - The identifier of the particular network on the Internet;
    - The identifier of the particular device (which can be a server or a workstation) within that network.
On the Internet (which is between the "Router" that move packets from one point to another along the route), only the network part of the IP address is looked at.

--------
The Network Part of the IP Address:

The Internet is really the interconnection of many individual networks (it's sometimes referred to as an internetwork). So the Internet Protocol (IP) is basically the set of rules for one network communicating with any other netwok; or occasionally, for broadcast messages, one network communicating with all other networks.

Each network must know its own address on the Internet, and the address of any other networks with which it communicates.

To be part of the Internet, an organization needs an Internet network number, which it can request from the Network Information Center (NIC). This unique network number is included in any packets sent out of the network onto the Internet.

--------
The Local/Host Part of the IP Address:

In addition to the network address or network number, information is needed about which specific machine/host in a network is sending or reciving a message.

So the IP address needs both the unique "Network Number" and a "Host Number" which is also unique within the network.

The host number is sometimes called a "Local Address" or "Machine Address".

--
Part of the Local Address can identify a subnetwork or subnet address, which makes it easier for a network that is devided into several physical subnetworks -- For example, serveral different local area networks -- to handle many devices.

--------
IP Address Classes and Their Format:

Since networks vary in size, there are four different address Formats/Classes to consider, when applying to Network Information Center (NIC) for a network number:

    - Class A addresses are for large networks with many devices.

    - Class B addresses are for medium-sized networks.

    - Class C addresses are for small networks (which is fewer than 256 devices).

    - Class D addresses are multicast addresses.

The first few bits of each IP address indicate which of the Address Class Format it is using.

--
The address structure look like this (32-bits in total -- i.e. IPv4):

- Class A:
+------+-------------------+-------------------------+
|    0 | Network (7 bits)  | Local Address (24 bits) |
+------+-------------------+-------------------------+

- Class B:
+------+-------------------+-------------------------+
|   10 | Network (14 bits) | Local Address (16 bits) |
+------+-------------------+-------------------------+

- Class C:
+------+-------------------+-------------------------+
|  110 | Network (21 bits) | Local Address (8 bits)  |
+------+-------------------+-------------------------+

- Class D:
+------+---------------------------------------------+
| 1110 | Multicast Address (28 bits)                 |
+------+---------------------------------------------+

The IP address is usually expressed as four Decimal Numbers, each representing eight bits, separated by "Periods". This is sometimes known as the "Dot Address". More technically, is known as "Dotted Quad Notation".

- For Class A IP Addresses, the numbers would represent "network.local.local.local";
- For Class C IP Addresses, the numbers would represent "network.network.network.local".

The number version of the IP address can (and usually is) represented by a name or series of names called the Domain Name.

----
The Internet's explosive growth makes it likely that: without some new architecture, the number of possible network addresses using the scheme above would soon be used up (at least for Class C network addresses, because there are only 8 bit left for local address part of the IP address, meaning much fewer subnets).

However, a new IP version -- IPv6 -- expands the size of the IP address to 128 bits, which will accommodate a large growth in the number of network addresses.

For hosts still using IPv4, the use of "Subnets" in the Host/Local Part of the IP Address will help reduce new applicatopns for network numbers.

In addition, most sites on today's mostly IPv4 Internet have gotten around the Class C network address limitation by using the Classless Inter-Domain Routing (CIDR) scheme for address notation.

--------
Relationship of the IP Address to the Physical Address:

The machine or physical address used within an organiztion's local area networks may be DIFFERENT than the Internet's IP address.

The most typical example is the 48-bit Ethernet address. TCP/IP includes a facility called the Address Resolution Protocol (ARP) that lets the adminstrator create a table that maps IP addresses to physical addresses. The table known as the ARP cache.

--------
Static v.s. Dynamic IP Addresses:

The discussion above assumes that IP addresses are assigned on a static basis. In fact, many IP addresses are assigned dynamically from a pool.

Many corporate networks and online services economize (spend less) on the number of IP addresses by sharing a pool of IP addresses among a large number of users.


<EOF>
========
CIDR (Classless Inter-Domain Routing/ Supernetting):
[web link: https://searchnetworking.techtarget.com/definition/CIDR]

----
Classless Inter-Domain Routing (CIDR), also known as Supernetting, is a method of assigning IP Addresses, which improves the efficiency fo address distribution and repalces the previous system based on Class A, B, and C networks.

The initial goal of Classless Inter-Domain Routing (CIDR) was to slow the increase of routing tables on routers across the Internet, and decrease the rapid exhaustion of IPv4 addresses.

As a result, the number of available Internet addresses has greatly increased.

----
The original classful network design of the Internet include ineffciencies that drained the pool of unassigned IPv4 addresses faster than necessary.

The classful design include the following:
    - Class A, with over 16 million identifiers;
    - Class B, with 65,535 indentifiers;
    - Class C, with 254 host identifiers (2^8=256).

If an organization needed more than 254 host machines, it would be switched into Class B. However, this couls potentially waste over 60,000 hosts if the business didn't need to use them, which is unnecessarily decreasing the availability of IPv4 addresses.

Classless Inter-Domain Routing (CIDR) was introduced by the Internet Engineering Task Force (IETF) in 1993 to fix this problem.












