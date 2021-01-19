This archive is based on: https://whatis.techtarget.com/definition/traceroute

--------
Traceroute is a utility, that records the route through the Internet between your computer and a specified destination computer (i.e. the route is the specific gateway computers at each hop).

Traceroute also calculates and displays the amount of time each hop tool.

----
Hop:
[wen link: https://whatis.techtarget.com/definition/hop]

In a packet-switching network, a hop is the trip a data packet takes from one router/intermediate point to another in the network. On the Internet (or a network that uses TCP/IP), the number of hops a packet has taken toward its destination (i.e. "hop count") is kept in the packet header. A packet with an exceeding large hop count is discarded.

Using Cellular Digital Packet Data (CDPD), a hop is a switch to another radio frequency (RF) channel.


--------
Back to Traceroute:

Traceroute is a handy tool both for understanding where problems are in the Internet network, and for getting a detailed sense of the Internet itself.

Another utility "Ping" is often used prior to using "Traceroute" to see whether a host is present on the network.

----
The traceroute utility comes included with a number of operating systems, including Windows and UNIX-based operating systems, or as part of a TCP/IP package.

If your system doesn't include traceroute utility, you can install it. There are freeware versions that you can download.


--------
How traceroute works:

    - When you entern the traceroute command, the utility initiates the sending of a packet, using ICMP.

    - Including this packet a time limit value (TTL) that is designed to be exceeded by the first router receives it, which will return a "Time Exceed Message". This enabled traceroute to determine the time required for the hop to the first router.

    - Increasing the time limit value (TTL), it resends the packets, so that the packet will reach the second router in the path to the destination, which returns another "Time Exceed Message", and so forth.

    - Traceroute determines when the packet has reached the destination, by including a "port number" that is outside the normal range. When the packet is received, a "Port Unreachable Message" is returned, enabling traceroute to measure the time length of the final hop.

    - As the tracerouting progresses, the records are displayed for you hop by hop. Actually, each hop measured three times. If you see an asterisk (i.e. *), this indicates a hop that exceeded some limit.


----
If you have a Windows operating system, try traceroute out by clicking on Start-->Programs-->MA-DOS Promot, and then at the C:WINDIWS promot, enter:
    tracert www.whatis.com

Or whatever domain name for a destination host computer you want to enter.

You can also enter the equivalent numeric form of the IP address.



<EOF>
