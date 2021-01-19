This archive is based on: https://searchnetworking.techtarget.com/definition/subnet

--------
Subnet/Subnetwork:

A subnet/subnetwork is a segmented piece of a larger network. More specifically, subnets are a logical partition of an IP network into multiple smaller network segments.

The Internet Protocol is a method for sending data from one computer to another over the Internet. Each computer/host has at least one IP address as a unique identifier.

----
Organizations will use a subnet to subdivide large networks into smaller, more efficient subnetworks. One goal of a subnet is to split a large network into grouping of smaller interconnected networks to help minimize traffic. This way, traffic dosen't have to flow through unnecessary routes, increasing network speeds.

    - Subnetting, the segmentation of a network address space, improves address allocation efficency.
    - Subnetting is described in the formal document, Requset for Comments 950;
    - Subnetting is tightly linked to IP addresses, Subnet Masks, and CIDR notation.

--------
Benefits uses of subnets:

    - Reallocating IP address:

Each class has a limited number of host allocations. For example, networks with more than 254 devices need a Class B allocation (which at most can have 254 hosts). If a adminstrator is working with a Class B or C network, and needs to allocate 150 hosts for three physical networks located in three different city. They would need to either request more address blocks for each network, or divide a network into subnets that enable adminstrators to use one block of addresses on multiple physical networks.

[web link: https://www.techopedia.com/definition/3991/ip-address-blocking]
(IP addressing blocking is a security measure that prevents a connection between a specific or group of IP addresses and a mail, web, or Internet server. This is usually done to ban or block any undesirable sites and hosts from entering the server or node and causing harm to the network or individual computers.)

    - Relieving network congestion:

If much of an organization's traffic is meant to be shared regularly between the same cluster of computers, placing them on the same subnet can reduce network traffic. Without a subnet, all computers and servers on the network would see data packets from every other computer.

    - Improving network security:

Subnetting allows network adminstrators to reduce network-wide threats by quarantining compromised sections of the network, and by making it more diffcult for trespassers to move aroud an organization's network.


=================================================
How to calculate a Subnet Mask from Hosts and Subnets:
[https://searchnetworking.techtarget.com/tip/IP-addressing-and-subnetting-Calculate-a-subnet-mask-using-the-hosts-formula]

--------
IP addressing and subnetting are important and basic elements of networks. In this article, learn how to calculate a Subnet Mask based on the required number of Subnets and Hosts.

    - We explore IP addressing and subnetting;
    - We show how to apply this valuable information to real-world scenarios;
    - We address how to calculate a Subnet Mask by using Host and Subnet formulas.

--------
What is subnetting?

ISPs allocate IP address range to organizations based on the potential number of Networls and Hosts/Endpoints that organizations require. 

Today, the allocations follow the Classless Inter-Domain Routing (CIDR) assignment method.

----
The organization then subdivides the allocated address space into smaller allocations for each Subnetwork within the organization, using a process called "subnetting".

The result of subnetting is the number of subnetworks increases, while the number of usable host IP addresses decrease. Each subnetwork is known as an "IP Subnet".

--------
Why use subnetting?

Subnetting enables assigned network addresses to be broken into smaller efficient allocations that are more suitable for each network within the organization. 	For example, a point-to-point WAN link between two routers only needs two addresses, while a LAN segment may need to support many hosts, such as Servers, Workstations, Laptops, and Wi-Fi-connected Mobile Devices.

----
Subnetting and "Route Summarization" work together to make routers more efficient by reducing the size of routing tables.

Routers far away from a "Destination" don't need much addressing detail, so routers can be summarized to a large degree. But, as packets get closer to the "Destination" network, routers will need more local routing information, such as the "Local Subnet Mask". By applying the mask to a packet's destination address, routers can determine which specific network segment contains the destination host and properly deliver the packet.

--------
Next, let's review some background information, including what network adminstrators need to know about IP addressing and subnetting. Let's start with a review of some basic elements of IP addressing and subnetting:

    - IP addresses must be unique on the Internet when using public IP addresses and on a private network when using private IP addresses.

    - IPv4 addresses are 32-bits made up of 4 octets of 8 bits each. To calculate the Subnet Mask, convert an IP address to biniary, perform the calculation and then convert back to the IPv4 decimal number representation known as a "dotted quad". The same subnetting procedure works for IPv6 addresses.

    - A subnet mask tells the computer what part of the IP address is the network portion of the address, and what part identifies the host address range (which are addresses that are assigned to host computers on that network. A longer subnet mask -- meaning more 1 bits in the mask -- creates more IP subnets that have a smaller host address block size.

    - Subnetting breaks a large network into smaller networks by extending the length of the subnet mask. This increases the number of subnetworks, while reducing the number of hosts per subnet. Organizations will typically use serveral different subnet masks for different sizes of networks. For example, a point-to-point link with only two devices would use a 31-bit mask (1-bit for host). An office LAN or data center LAN, however, would use a shorter subnet mask that allows more hosts. Determining the tradeoff between the number and size of subnets is explained below.

    - Today, classless IP addresses with "variable-length subnet masks (VLSM)" are used almost exclusively; and classful IP addresses - known as either Class A network, Class B network, Class C network -- are used only for certification testing or older routing protocols. A Class D network is used for multicast; and there is an experimental allocation known as Class E.

    - A default gateway is a device, typically a router, where hosts send packets that are destined for a device not on the local LAN. Again, the device (gateway) knows what is and what is not on the local LAN by using its assigned subnet mask to compare its local IP address and subnet with the destination's IP address and subnet.

    - Private IP addresses, also known as Request for Comment 1918 addresses, are used by most networks today. Thses special IP addresses are not routable over the Internet; and must be translated to public IP addresses when those devices need to talk to the Internet, either through a "Proxy Server" or through "Port Address Translation".

--------
Using the Host's formula:

A common, real-world question when laying out your network is: "What subnet mask do I need for my network?" To answer this question, let's learn how to use the host's formula.

The host's formula will tell you how many hosts will be allowed on a network that has a certain subnet mask.

    - The host's formula is: 2^h -2
      The "h" represents the number of 0s in the subnet mask, if the subnet mask were converted to binary.

    - The first and last addresses are reserved.
      The first to identify the network; The last to be used as the broadcast address.

--------
Step 1. Find host range

To use the host's formula, let's first look at a simple example. Say you plan to use the IP address space 192.168.0.0. Currently, you have a small network Subnet with 20 hosts. This network will grow to 300 hosts within the next year. However, you also plan to have multiple locations of a similar size in the future and need to enable them to communicate using this address space.

    - With a single network subnet and only 20 hosts, the simplest thing to do would be to use 255.255.255.0 as your subnet mask.

    - This would mean you would have "192.168.0.1" through "192.168.0.254" for your hosts (254 hosts in total).

    - The address "192.168.0.0" is reserved as the network Subnet identifier.

    - The address "192.168.0.255" is reserved for the network broadcast address.

--------
Step 2. Convert to binary

Before you decide to use this subnet mask, however, let's apply the host's formula to it. To use the host's formula in this scenario, you take the subnet mask 255.255.255.0 and convert it to biniary. This would give you: 11111111 11111111 11111111 0000000.

    - As you can see, there are eight 0s in the subnet mask. To use this with the host's formula, you would calculate 2^8 - 2.

    - This comes to 256 minus the 2 reserved addresses, or 254.

    - So, with the subnet mask specified, you would get 254 usable hosts.

This would suit your 20-user network now but won't support your future network expansion to 300 hosts.

--------
Step 3. Calculate the total number of hosts per subnet

You should plan ahead and choose the best subnet mask the first time. This prevents you from having to go back later and change all the IP addresses on this network.

Adding 1s to the subnet mask means you get fewer hosts per network Subnet, but more network subnets. If you remove 1s from the subnet mask, you get more hosts per network, but fewer network subnets. In this case, the latter is what we need to do.

    - To do this, let's take away one of the 1s to make our subnet mask:
      11111111 11111111 11111110 00000000

    - In decimal number, or dotted quad representation, this is 255.255.254.0

    - This means you have nine 0s in the host portion of the subnet mask. To apply the host's formula with this new subnet mask, we'd calculate 2^9 -2. The number of usable host IP addresses is 512 minus 2, or 510.

This would definitely suit a 20-user network now and future network which host expectations of 300 hosts.

----
Considering that information, we know the most efficient subnet mask for this network is 255.255.254.0. The valid host address range for each subnet must be written as two ranges, due to the limitations of writing the addresses as dotted quads.

    - The first IP subnet range would be "192.168.0.1" through "192.168.0.255" (255 hosts in first range);

    - The second IP subnet range would be "192.168.1.0" through "192.168.0.254" (255 hosts in second range);

    - "192.168.0.0" identifies the subnet.

    - "192.168.1.255" is the network broadcast address.

This is how you arrive at the total of 510 usable hosts.

--------
Step 4. Calculate the number of subnets

Now that you understand the host's formula, you should also know the subnet's formula, which ensure you have the right subnet mask for the number of subnets that you have.

Just because you determine you have the right number of hosts for your LAN using the host's formula doesn't mean you'll have enough subnets for your network.

----
Let's see how the subnet's formula works:

The subnet's formula is 2^s, where "s" is the number of 1s added to the subnet mask, from whatever the subnet mask was.

----
Let's take the same example as above, but build on it:

Using network 192.168.0.0, we expect to have 100 remote sites with 300 PCs each. What subnet mask should we use?

In our last example, we found the 255.255.254.0 subnet mask provided 510 hosts per subnet. That was more than adequate to support 300 PCs, but dose that same subnet mask provide networks for at least 100 remote sites?

--------
Step 5. Verify the total number of subnets

The number of subnets is found by counting bits by which the initial mask was extended, also known as the "Subnet Bits".

----
Our initial address Allocation was 192.168.0.0 with a mask of 255.255.0.0.

Using the host's formula, we selected a subnet mask of 255.255.254.0 (for 510 usable hosts).

Let's compare the two subnet masks, and counet the "Subnet Bits":
    - 255.255.0.0   = 11111111 11111111 00000000 00000000
    - 255.255.254.0 = 11111111 11111111 11111110 00000000

The new mask uses seven Subnet Bits (7 more 1s). Using the subnet's formula, this would give us 2^7=128 networks. So we have enough subnets for 100 remote networks. This means we have found the right subnet mask for our network, which is 255.255.254.0.

----
As you add subnet bits, the number of subnets increases by a factor of two (^2), and the number of hosts per subnet decreases by a factor of two.

The table below shows thw number of subnets and hosts for EIGHT(8) mask bits in THIRD(3rd) octet of IPv4 address.
+---------------+-----------------------------------------+---------------+------------------+
| MASK          | BINARY (8 mask bits in 3rd octet)       | SUBNETS (2^s) | HOSTS (2^h -2)   |
+---------------+-------------------+----------+----------+---------------+------------------+
| 255.255.0.0   | 11111111 11111111 | 00000000 | 00000000 | 1 = 2^0       | 65,534 = 2^16 -2 |
+---------------+-------------------+----------+----------+---------------+------------------+
| 255.255.128.0 | 11111111 11111111 | 10000000 | 00000000 | 2 = 2^1       | 32,766 = 2^15 -2 |
+---------------+-------------------+----------+----------+---------------+------------------+
| 255.255.192.0 | 11111111 11111111 | 11000000 | 00000000 | 4 = 2^2       | 16,382 = 2^14 -2 |
+---------------+-------------------+----------+----------+---------------+------------------+
| 255.255.224.0 | 11111111 11111111 | 11100000 | 00000000 | 8 = 2^3       | 8,190 = 2^13 -2  |
+---------------+-------------------+----------+----------+---------------+------------------+
| 255.255.240.0 | 11111111 11111111 | 11110000 | 00000000 | 16 = 2^4      | 4,094 = 2^12 -2  |
+---------------+-------------------+----------+----------+---------------+------------------+
| 255.255.248.0 | 11111111 11111111 | 11111000 | 00000000 | 32 = 2^5      | 2,046 = 2^11 -2  |
+---------------+-------------------+----------+----------+---------------+------------------+
| 255.255.252.0 | 11111111 11111111 | 11111100 | 00000000 | 64 = 2^6      | 1,022 = 2^10 -2  |
+---------------+-------------------+----------+----------+---------------+------------------+
| 255.255.254.0 | 11111111 11111111 | 11111110 | 00000000 | 128 = 2^7     | 510 = 2^9 -2     |
+---------------+-------------------+----------+----------+---------------+------------------+
| 255.255.255.0 | 11111111 11111111 | 11111111 | 00000000 | 256 = 2^8     | 254 = 2^8 -2     |
+---------------+-------------------+----------+----------+---------------+------------------+

========
Variable-length subnetting:

Most networks require subnets of several different sizes, sometimes called variable-length subnet masks. This is easily accomplished by taking one of the larger subnets (a subnet with a shorter mask), and applying the subnetting algorithm to it.

This is known as variable-length subnetting since the network will have subnet masks of several length.

====
Extending the example from above, let's say that most of the 100 sites also require two point-to-point WAN links (i.e. 200 sub-subnets with two hosts each) -- a router on each end of the link.

We are starting with a subnet mask of 255.255.254.0. Using the host's formula, we need two host bits (calculated by 2^2-2=2), which means two 0s in the sub-subnet mask (i.e. 255.255.255.252).

Extending the (1st) subnet mask results in the following in binary:
    - 255.255.254.0   = 11111111 11111111 11111110 00000000
    - 255.255.255.252 = 11111111 11111111 11111111 11111100

The (1st) subnet mask was extended by seven bits (7 more 1s than 255.255.254.0). Using the subnet's formula of 2^s, we have 2^7=128 sub-subnets.

====
This isn't enough for all our WAN links (we need 200 sub-subnets), so we do the same thing with another large subnet (i.e. 255.255.252.0, which is a smaller subnet mask in 3rd octet than 255.255.254.0 itself) for more sub-subnets.

Extending the (2nd) subnet mask results in the following in biniary:
    - 255.255.252.0   = 11111111 11111111 11111100 00000000
    - 255.255.255.252 = 11111111 11111111 11111111 11111100

The (2nd) subnet mask was extended by 8 bits (more 1s in 255.255.255.252 than 255.255.252.0), we now have 2^8=256 sub-subnets (we only need half -- 128 sub-subnets in 255.255.252.0 subnet, another half is already in 255.255.254.0 subnets).

====
If we reserved the top two large subnets (i.e. whose subnet masks are 255.255.254.0 and 255.255.252.0) to be subnetted for WAN links, we would have enough capacity for 128*2=256 point-to-point links (which means 256 subnets, 2 hosts per subnet).

Network Address: 192.168.0.0
1st Subnet Mak: 255.255.254.0 = 11111111 11111111 11111110 00000000
2nd Subnet Mak: 255.255.252.0 = 11111111 11111111 11111100 00000000

+---------------+-------------------------------------+-------------------------------------+-----------------+
| subnet mask   | subnet mask to binary               | 128 = 2^7 sub-subnets (7 more 1s)   | sub-subnet mask |
+---------------+-------------------------------------+-------------------------------------+-----------------+
| 255.255.254.0 | 11111111 11111111 11111110 00000000 | 11111111 11111111 11111111 11111100 | 255.255.255.252 |
+---------------+-------------------------------------+-------------------------------------+-----------------+
| 255.255.252.0 | 11111111 11111111 11111100 00000000 | 11111111 11111111 11111101 11111100 | 255.255.253.252 |
+---------------+-------------------------------------+-------------------------------------+-----------------+
| P.S. last twe 0s is for hosts in each sub-subnet.                                                           |
+-------------------------------------------------------------------------------------------------------------+

Host IP range as following:
    - 192.168.252.0 through 192.168.253.254: WAN subnets 0 through 127
    - 192.168.254.0 through 192.168.255.254: WAN subnets 128 through 255

====
The same process can be used if we have many small remote sites that have few hosts at each site, such as in a retail business.

It is important to assign subnets to sites in a way that enables address summarization that reduces routing table size and increases router efficiency.

--------
Support for 31-bit masks:

Morden routers also support using a 31-bit subnet mask (255.255.255.254) for point-to-point links because a broadcast address is not needed on a point-to-point link (e.g. the first and last addresses is no need to be reserved for subnet and broadcast, only for two hosts).

This configuration is an exception to the rule that reserves two addresses: one address to identify the subnet and another for the broadcast address.

--------
Classless Inter-Domain Routing(CIDR):

    - CIDR eliminates the original classful designation of IPv4 addresses.

    - CIDR enables a single network prefix and mask to represent an aggregation of multiple networks. This is also called "supernetting".

    - CIDR addresses representation simplifies the representation of an address and mask.

    - CIDR also support network aggregation and address summarization.

----
Network summarization -- Supernetting and wildcard masks
[web link: https://searchnetworking.techtarget.com/tip/Network-summarization-Supernetting-and-wildcard-masks]
[See archive about Supernetting for details.]

----
CIDR notation appends the number of subnet mask bits to the network address.

Instead of wirting the address and mask using dotted notation, we append a forward slash "/" and the number of bits in the subnet mask.

In our previous example of 100 subnets that support over 300 hosts each, we find that the subnet mask contains 23 bits.
    - host IPv4 address: 192.168.0.1   = 11000000 10101000 00000000 00000001
    - subnet mask:       255.255.254.0 = 11111111 11111111 11111110 00000000
    - written in CIDR:   169.168.0.1/23

--------
Calculating the subnet prefix:

Routers calculate the subnet address as part of the process to determine which interface to use to forward packets to their destination.

In this process, a binary AND operation is performed on an address and its mask. The result is the prefix, which removes all the host bits.

The router uses the network prefix to find the routing table entry that best matches the prefix (i.e. the longest match or the default route).

The packet is forwarded out the interface that is associated with the best match prefix.

====
Example depicts subnet mask calculation and proper routing procedures:

    - R1 (router 1) receives a packet addressed to 192.168.5.19/23 (a host that's connected to R2's LAN).

    - R1 using a binary AND operation on the address and its mask to determine the route prefix:
      ip address:   192.168.5.19  = 11000000 10101000 00000101 00010011
      subnet mask:  255.255.254.0 = 11111111 11111111 11111110 00000000
      route prefix:                 11000000 10101000 00000100 00000000 = 193.168.4.0

    - R1 looks up in its Routing Table according to the route prefix:
      +--------+---------------+---------------+-----------------+---------+
      | Prefix | 192.168.2.0   | 192.168.4.0   | 192.168.252.0   | 0.0.0.0 |
      +--------+---------------+---------------+-----------------+---------+
      | Mask   | 255.255.254.0 | 255.255.254.0 | 255.255.255.252 | 0.0.0.0 |
      +--------+---------------+---------------+-----------------+---------+

    - R1 finds 192.168.4.0 in its routing table (longest match) and forwards the packet out the S0 interface to R2.

    - R2 will do the same prefix calculation and determine that it shoud send the packet on interface E0 and taht is a local delivery to host 5.19.

--------
Large-scale network design:

In the real world, you will probably never have the chance to design a large network such as this scratch. However, large-scale network design skills are valuable for various reasons:

    - Understanding the subnetting of a large-scale network that is already implemented;
    - Understanding what effect making changes to a network, its IP addressing and its subnetting will have;
    - To prove in a certification test that you understand IP addressing and subnetting, and can apply them (i.e. certifications like Cisco Certified Network Associate require you to apply these skills and calculate IP addressing without a calcultor).

It is important to understand subnetting and be able to calculate masks, host ranges and subnets longhand, but we frequrntly verify our calculations with a subnet calculator.


<EOF>












