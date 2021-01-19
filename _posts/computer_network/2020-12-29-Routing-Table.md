This archive is based on: https://searchnetworking.techtarget.com/definition/routing-table

--------
A routing table is a set of rules, often viewed in table format, that is used to determine where data packets traveling over an Internet Protocol (IP) network will be directed.

All IP-enabled devices, including routers and switches, use routing table.

    - A routing table contains the information necessary to forward a packet along the BEST path toward its destination.
    - Each packet contains information about its origin and destination.
    - When a packet is received, a network device examines the packet and matches it to the routing table entry providing the best match for its destination.
    - The table then provides the device with instructions for sending the packet to the next hop on its route across the network.

----
A basic routing table includes the following information:

    - Destination:
      The IP address of the packet's final destination.

    - Next hop:
      The IP address to which the packet is forwarded.

    - Interface:
      The outgoing network interface the device should use when forwarding the packet to the next hop or final destination.

    - Metric:
      Assigns a cost to each available route so that the most cost-effective path can be chosen.

    - Routes:
      Includes directly-attached subnets;
      indirect subnets that are not attached to the device but can be accessed through one or more hops;
      default routes to use for certain types of traffic or when information is lacking.

----
Routing tables can be maintained manually or dynamically.

    - Tables for static network devices do not change unless a network adminstrator manually changes them.

    - In dynamic routing, devices build and maintain their routing tables automatically by using Routing Protocols to exchange information about the surrounding network topology. Dynamic routing tables allow devices to "listen" to the network and respond to occurrences (an incident or event) like device failures and network congestion.


<EOF>
