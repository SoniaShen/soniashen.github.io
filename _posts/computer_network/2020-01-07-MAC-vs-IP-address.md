This archive is based on: https://searchnetworking.techtarget.com/answer/What-is-the-difference-between-an-IP-address-and-a-physical-address

--------
Every computer or device on the Internet has two types of addresses:
    Its physical address and its Internet address.

    - The physical address, which is also called a Media Access Control Address, identifies a device to other devices on the "same local" network.

    - The Internet address, i.e., IP address, identifies the device "globally".

A network packet needs both addresses to get to its destination.

----
Any piece of Internet software, such as a web browser, directs data to a destination on the Internet using the destination's IP address. That address is inserted into the data packets that the network software stack sends out.

People rarely use the address numbers directly, instead using DNS names, which the application translates into the matching number.

Internet routers move the packets from the source network to the destination network, and then to the LAN on which the destination device is connected. That local network (of destination) translates the IP address to MAC address, adds the MAC address to the data stream, and send the data to the right device.


--------
What is a MAC address:

Media access control refers to the piece of "hardware (interface)" that controls how data is pushed out onto a network.

In the OSI reference model for netowrking, the MAC is a Layer 2 device, the MAC address is a Layer 2 address. In the current Internet era, most devices are connected physically with Ethernet cables or wirelessly with Wi-Fi. Both methods use MAC addresses to identify a "device" on the network.

    - A MAC address consists of 12-hexadecimal-digits, usually grouped into 6 pairs separated by hyphens (-);

    - MAC addresses are available from 00-00-00-00-00-00 through FF-FF-FF-FF-FF-FF;

    - The first half of the number is typically used as a "manufacturer ID";

    - The second half of the number is a "device identifier".

In nearly all enterprise network devices today, whether Wi-Fi or Ethernet, this MAC number is hardcoded into the device during the manufacturing process.

----
Each MAC address is unique to the "Network Card" installed on a device. But the number of "device identifying bits" is limited, which means manufacturers do reuse them.

Each manufacturer has about 1.68 million available addresses, so when it burns a device with a MAC address ending in FF-FF-FF (device identifier), it starts again at 00-00-00.

This apporach assumes it is highly unlikely two devices with the same (MAC) address will end up in the same "local netowrk" segment.

----
No two devices on a "local network" should ever have the same MAC address. If that dose happen, both devices will have communications problems because the local network will get confused about which device shold receive the packet.

When a "switch" broadcasts a packet to all "ports" in order to find the intended recipient, whichever device responds first will receive the packet stream directed to it. If the (first respond) device reboots/taken away/shuts down, the other node may then receive the packets.


--------
What is an IP address:

IP controls how devices on the Internet (global) communicate, and defines the behavior of "Internet routers".

IP address corresponds to Layer 3, the network layer, of the OSI reference model. The Internet was initially built around IPV4 and is in transition (adaption) to IPV6.

[web link: https://searchnetworking.techtarget.com/tip/Understanding-why-IPv6-renumbering-problems-occur]

----
An IP address identifies a device on the global Internet.

IPv4:
    - An IPv4 address consists of 32-bits, usually written as 4 decimal numbers, or a dotted quad;

    - Possible values range from 000.000.000.000 through 255.255.255.255;

    - Although many possible addresses are disallowed or reserved for specific purposes;

    - The address combines "network identification" and "device identification" data;

    - The netwrok prefix is anywhere from 8 (255.0.0.0) to 31 (/31) bits, and the remainder identify the device on the network.

Steady, rapid growth in the number of Internet-connected devices has led to the looming exhaustion of the IPV4 address space, one of several reasons for the development of IPv6.

IPv6:
    - An IPv6 address consists of 128-bits;

    - The first 64 bits reserved for "network identification";

    - The second 64 bits dedicated to identifying a device on the network;

    - The address is written as eight sets of four hexadecimal digits separated by colons (:).
      For example: FEDC:BA98:7654:3210:0123:4567:89AB:CDEF

Happily, many conventions (habits) are available to shorten an IPv6 address when writing it.


--------
MAC address v.s. IP address:

Both MAC addresses and IP addresses are meant to identify a network device, but in different ways. A MAC address is responsible for "local identification", and an IP address for "global identification". This is the primary difference between a MAC address and IP address.

It affects how they differ in their numbers of bits, address assignment, and IP interactions.

The MAC address is only significant (maenful) on the LAN to which a device is connected, and MAC address is not used or retained in the data stream once packets leave that network.

----
Another difference between a MAC address and IP address is the way the addresses are assigned.

    - An IP address is bound to a network device via software configurations, it can be changed at any time;

    - "Local network switches" maintain Address Resolution Protocol (ARP) tables that map IP addresses to MAC addresses;

    - When a "router" sends the "switch" a packet with a destination specified by an IP address, it (swith) uses the ARP table to know which MAC address to attach to the packet when it forwards the data to the device as "Ethernet frams".




<EOF>
