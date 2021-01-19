This archive is based on: https://www.happyrouter.com/network-summarization-supernetting-and-wildcard-masks

--------
Network Summrization - Supernetting and wildcard masks:

Supernetting was created as a way to solve the problem of routing tables growing beyond our current ability to manage the exhaustion of Class B network address space.

Much like one area code represents an aggregation of telephone numbers in an area, "supernetting" allows one routing table entry to represent an aggregation of networks.

----
If you need to enter a static route to several subnetted networks, you can use netwrok summrization to reference them all in one route.

    - You need to understand how to read "Routes" from other providers;
    - YOu must also know how to create an "Access List" that references these multiple networks in a summrized statement.


--------
Network Summarization Terminlogy v.s. Supernetting:

    - The term "route aggregation" is just another word of saying "network summarization". 

    - "Supernetting", on the other hand, is the process to taking multiple networks, and making a single larger network.

----
Network Summarization is the act of taking two or more IP networks, and using a single IP network to represent them all.

Network Summarization is possible because of CIDR:
    - CIDR eliminates the need for a fixed-length subnet mask (FLSM) assiciated with our IP networks. (Because classic Class A/B/C have to have a certain subnet mask.)

    - Because everyone uses CIDR today, we can use VLSMs. This means we have the luxury of adding/subtracting bits from our "Subnet Mask" to allow us to:
        - either subnet our network futher (by adding bits to subnet mask);
        - or supernet out network (by taking bits away from the subnet mask).


--------
What is "Route Aggregation", aka, "Network Summarization":

Say I have IP networks 1.1.1.0/24, and 1.1.2.0/24, and 1.1.3.0/24. All of these networks have the subnet mask of 255.255.255.0, hence, the /24.

This means that if I take away bits from the subnet mask, I can encompass (surround and have/hold within) both of these networks with a single IP network and subnet mask.

----
For example, I could say that these networks are represented by the IP address 1.1.0.0, with the subnet mask 255.255.0.0. With that statement, I have summarized/aggregated all three networks, and am now representing them with a single IP adderss (1.1.0.0) and subnet (255.255.0.0).

However, this is very inefficiently, I actually summarized many other networks besides the three in question. I summarized all networks that fit into this range 1.1.{0-255}.{0-255}.

To summarize only my three networks as efficiently as possible, I would use IP network 1.1.0.0, with subnet mask 255.255.252.0 (=11111111 11111111 11111100 00000000). This encompassea all three IP networks: 1.1.1.0, 1.1.2.0, 1.1.3.0.

Third octet of each IP and subnet mask:
    - 00000001 = 1
    - 00000010 = 2
    - 00000011 = 3
    - 11111100 = 252


--------
Using network summarization/aggregation on a Router:

To use aggregation on a router, you will represent the IP networks with a single, and wither a subnet mask or a wildcard mask.

----
Here is the same example of using a subnet mask to summarize the same three netwoks in OSPF:
    - Router(config)#        router ospf 1
    - Router(config-router)# area 1 range 1.1.0.0 255.255.252.0

As you can see, I just made an entry to summarize all three networks using the “range” command. The "range" command is used to summarize other OSPF networks.

----
The same example can be applied to summarizing networks received from a different router protocol like Routing Information Protocol (RIP).

Here’s an example with the “summary-address” command: 
    - Router(config-router)# summary-address 1.1.0.0 255.255.252.0 


--------
What are wildcard mask?

Wildcard masks are just another way to represent a subnet mask. You can easily convert a subnet mask into a wildcard mask.

A wildcard mask is simply all the 1s in a subnet mask turned into 0s, and all the 0s turned into 1s.

----
Here's an example:
    - Subnet mask in binary:      11111111 11111111 11111100 00000000 = 255.255.252.0
    - Converted to wildcard mask: 00000000 00000000 00000011 11111111 = 0.0.3.255

----
Wildcard masks are used in "access lists".

Say that I want to permit the same three networks we listed above and deny all others. Here is an example of an Access Control List (ACL) that would do that (using a wildcard mask):
    - Router(config)# access-list 1 permit 1.1.0.0 0.0.3.255
    - Router(config)# access-list 1 deny any

With this ACL, all three our networks (1.1.1.0, 1.1.2.0, 1.1.3.0) are premitted, and all other networks are denied.



<EOF>
