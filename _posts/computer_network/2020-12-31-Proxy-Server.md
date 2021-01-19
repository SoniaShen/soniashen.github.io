This archive is based on: https://whatis.techtarget.com/definition/proxy-server

--------
A proxy server is a dedicated (exclusively allocated/intended for a particular service or purpose) computer/ a software running on a computer that acts as an intermediary between an endpoint device (i.e. a computer) and another server from which a user/client is requesting a service.

The proxy server may exist in the same machine as a "firewall server", or it may be on a separate server which forwards requests through the firewall.

----
An advantage of a proxy server is that its cache can serve all users. If one or more Internet sites are frequently requested, these sites are likely to be in the proxy's cache, which will improve user response time.

A proxy server can also log its interactions, which can be helpful for troubleshooting.


--------
How proxy servers work:

When a proxy server receives a request for an Internet resource (i.e. a Web Page). It looks in its cache of previously pages. If proxy finds this page cache, it returns it to the user without needing to forward the request to the Internet.

If the requested page is not in the cache, the proxy server, acting as a client on behalf of the user, uses one of its own IP addresses to request the page from the server out on the Internet. When the page is returned, the proxy server relates it to the origianl request and forward it to the user.

----
Proxy servers are used for both legal and illegal purpose.

    - In the enterprise, a proxy server is used to facilitate security, administrative control, or caching services, among other purposes.

    - In personal computing context, proxy servers are used to enable "user privacy" and "anonymous surfing".

    - Proxy servers can also be used for the opposite purpose:
      To monitor traffic and undermine user privacy.

----
To the user, the proxy server is invisible, because all Internet requests and returned responses appear to be directly with the addressed Internet server. However, the proxy server is not actually invisible, since its IP address has to be specified as a configuration option to the browser/other protocol program.

Users can access web proxies online; or configure web browsers to constantly use a proxy server.

Browser settings include automatically detected and manual options for HTTP, SSL, FTP, and SOCKS proxies.

----
Proxy servers may serve many users, or just one per server. These options are called "shared and dedicated proxies", respectively. There are a number of reasons for proxies, and thus a number of types of proxy servers often in overlapping categories.


--------
"Forward" proxy servers:

    - Forward proxies send the requests of a client onward to a web server.

    - Users access "forward proxies" by directly suffering to a web proxy address, or by configuring their Internet settings.

Forward proxies allow circumvention (bypass) of firewalls. It increase the privacy and security for a user, but many sometimes be used to download illegal materials such as copyright materials/chlid pornography.

--------
"Reverse" proxy servers:

    - Reverse proxies transparently handle all requests for "resources on the destination servers" without requiring any action on the part of the requester.

    - A reverse proxy server relays connection requests for inbound (incoming) network traffic.

----
Reverse proxies are used:
    - To enable indirect access, when a website disallows direct connections as a security measure;
    - To allow for load balancing between servers;
    - To stream internal content to Internet users;
    - To disable access to a site, for example when an ISP/government wishes to block a website.

Sites might be blocked for more or less legitimate reasons. Reverse proxies may be used to prevent access to immoral, illegal, or copyright content.

Sometimes these reasons are justifiable and sometimes they are not. Reverse proxies sometimes prevent access to news sites where users could view leaked information. They can also prevent users from accessing sites where they can disclose information about government or industry actions. Blocking access to such website may violate free speech rights.


--------
Other types of proxy servers:

--
Transparent proxies:

Transparents proxies are typically found near the exit of a corporate network. These proxies centralized network traffic.

On corporate networks, a proxy server is associated with (or is a part of) a "gateway server" that separates the network from external networks (typically the Internet); and a "firewall" that protects the network form outside intrusion and allows data to be scanned for security purposes before delivery to a client on the network.

These transparent proxies help with monitoring and adminstering network traffic, as the computers in a corporate network are usually safe devices that do not need anonymity for typically mundane tasks.


--
Anonymouse proxies:

Anonymouse proxies hide the IP address of the client, using them allow to access to materials that are blocked by firewalls, or to circumvent IP address bans.

Anonymouse proxies may be used for enhanced privacy and/or protection from attack.


--
Highly anonymouse proxies:

Highly anonymouse proxies hide even the fact that they are being used by clients, and present a non-proxy public IP address.

So, not only do they hide the IP address of the client using them, they also allow access to sites that might block proxy servers. Examples of highly anonymouse proxies include: "I2P" and "TOR".


--
Socks 4 and 5 proxies:

Socks 4 and 5 proxies provide proxy service for UDP data and DNS look up operations in addition to Web traffic. Some proxy servers offer both Socks protocols.

[web link: https://whatis.techtarget.com/definition/socks]
Socks:

Socks (or "SOCKS" is a protocol that a proxy server can use to accept request from client users in a company's network, so that it can forward them accorss the Internet.

Socks uses sockets to represent and keep track of individual connections. The client side of SOCKS is built into certain Web Browsers; and the server side can be added to a proxy server.

A SOCKS server handles requests from clients inside a company's firewall, and either allows/rejects connection requests based on the requested Internet destination or user identification. Once a connection and a subsequent "bind" request have been set up, the flow of information exchange follows the usual protocol (i.e. HTTP protocol).


--
DNS proxies:

DNS proxies forward DNS request from LANs to Internet DNS servers, while caching for enhanced speed.


--------
Proxy server security:

Proxy servers in many forms enhance security but like many things in computing may be vulnerable themselves. To prevent DoS (Denial of Service) attack and network intrusion, adminstrators should keep software up to date; use load balancing; enforce (cause something to happen by necessity or force) secure authorization/authentication; and block unsolicited (not asked for) traffic/malicious (intending or intended to so harm)/open proxies.


--------
Proxies hacking:

In proxy hacking, an attacker attempts to steal hits from an authentic web page in a search engine's index and search results pages.

The proxy hacker would have a either a fraudulent (cheating/illegal/corrupted) site emulating the original or whatever they felt like showing the clients requesting the page. Here how it works:

    - The attacker creates a copy of the targeted web page on a proxy server, and uses method (such as "keywork stuffing") linking to the copied page from external sites, to artificially  raise its search engine ranking.

    - The authentic page will rank lower and may be seen as duplicated content, in which case a search engine may remove it from the index.

This form of hacking can also be used to deliver pages with malicious intent. Proxy hacking can direct users to fake banking sites, for example, to steal account info which can then be sold or used to steal funds from the account. The attacker can also use the hack to direct users to a malware-infected site to compromise their machines for a variety of nefarious (criminal) purposes.

----
Some means have been developed to compromised proxy abilities. Specially crafted "Flash and Java apps", "Javascript", "Active X", and some other browser plugins can be used to reveal (let out) a proxy user's identity. So proxies should not be used on untrusted sites or anywhere that anonymity is important.

----
Website owners who suspect they have been the victim of a proxy hack can test the theory by searching for a phrase (expression, a small group of words) that would be almost uniquely identifying to the site. Their site shoud be prominent (famous) on the search engine results page (SERP). If a second site with the same content shows up, it may be a proxy page.



<EOF>
