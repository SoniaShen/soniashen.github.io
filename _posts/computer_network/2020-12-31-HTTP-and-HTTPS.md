This archive is based on: https://whatis.techtarget.com/definition/HTTP-Hypertext-Transfer-Protocol

--------
HTTP:

Hypertext Transfer Protocol (HTTP) is the set of rules for transferring files on the World Wide Web, such as:
    - text;
    - graphic images;
    - sound;
    - video;
    - and other multimedia files.

----
As soon as a web user opens their web browser, the user is indirectly making use of HTTP.

HTTP is an application protocol that runs on top of the TCP/IP suite of protocols -- the foundation protocols for the Internet. The latest version of HTTP is HTTP/2, which was published in May 2015. It is an alternative to its predecessor HTTP 1.1, but dose not it make obsolete.


--------
How HTTP works:

As the Hypertext part of the name implies, HTTP concepts include the idea that files can contain references to other files whose selection will prompt (cause) additional transfer requests.

In addition to the Web page files it can serve, any Web Server machine contains an HTTP "daemon", a program that is designed to wait for HTTP requests and handle them when they arrive.

----
A web browser is an HTTP client, sending requests to server machines. When the browser user enters file requests by either "opening a web file" (typing in a URL), or clicking on a hypertext link, the browser builds an HTTP request and sends it to the IP address indicated by the URL.

The HTTP daemon in the destination server machine receives the request, and sends back the requested file or files associated with the request.

As a note, a web page often consists of more than one file.

----
To expand on this example, a user wants to visit "TechTarget.com":

    - The user types in the Web address, and the computer sends a "GET" request to a server that hosts that address. 

    - That "GET" request is sent using HTTP, and it is telling the "TechTarget" server that the user is looking for the "HTML code" used to structure and give the "login page" its look and feel.

    - The text of that "login page" is included in the HTML response. But other parts of the page, particularly its images and videos, are requested by separate HTTP requests and responses.

    - The more requests that must be made. For example, to call a page that has numerous images. The longer it will take the server to respond to those requests, and for the user's system to load the page.

----
When theses requests and responses are being sent, they use TCP/IP to reduce and tranport information in small packets of binary sequences of 1s and 0s. These packets are physically sent through electric wires, fiber optic cables, and wireless networks.


--------
Types of Status Code:

In response to HTTP requests, servers often issue response codes, indicating the request is being processed; that there was an error in the request; or that the request is being redirected.

Common response codes include:
    - 200 OK:
      This means that the request, such as "GET" or "POST", worked and is being acted upon.

    - 300 Moved permanently:
      This response code means that the URL of the requested resource has been changed permanently.

    - 401 Unauthorized:
      The client (i.e., the user making the request of the server) has not been authenticated.

    - 403 Forbidden:
      The client's identity is known but has not been given access authorization.

    - 404 Not Found:
      This is the most frequent and most recognized error code. It means that the URL is nor recognized or the resource at the location dose not exist.

    - 500 Internal Server Error:
      The server has encountered (run into) a situation it dosen't know how to handle.



.========
[web link: https://searchsoftwarequality.techtarget.com/definition/HTTPS]

HTTPS:

HTTP over SSL or HTTP secure (HTTPS) is used of Secure Socket Layer (SSL) or Transport Layer Securoty (TLS) as a sublayer under regular HTTP application layering.

----
HTTPS encrypts and decrypts user page requests, as well as the pages that are returned by the Web server.

The use of HTTPS protects against eavedropping and man-in-the-middle attacks. HTTPS was developed by Netscape.

HTTPS and SSL support the use of X.509 digital certificates from the "server", so that if necessary a user can authenticate the sender.

----
HTTPS uses port 443 instead of HTTP port 80 in its interacrion with the lower layer "TCP/IP".


--------
How HTTPS works:

Suppose you visit a Web site to view their online catalog:
    - When you're ready to order, you will be given a Web page "order form" with a URL that starts with "https://".
    - When you click "Send", to send the page back to the catalog retailer, your browser's HTTPS layer will encrypt it.
    - The "acknowledgement" you receive from the server will also travek in encrypted form, arrive with an "https://" URL.
    - The "acknowledgement" can be decrypted for you by your browser's HTTPS sublayer.

----
The effictiveness of HTTPS can be limited by poor implementation of browsers/server software, or a lack of support for some algorithms.

Furthermore, although HTTPS secures data as it travels between the server and the client, once the data is decrypted at its destination, it is only as secure as the host computer.

----
HTTPS is not to be confused with S-HTTP, a security-enhanced version of HTTP, which is developed and proposed as a standard by EIT.


--------
Getting started with HTTPS:

To explore how HTTPS is used in the enterprise, here are some additional resources for learning about HTTPS and Web page security:

    - Enabling HTTPS in J2EE Web components:
      The HTTPS protocol is a valuable security feature for J2EE Web components. Expert Ramesh Nagappan explains how to implement HTTPS in JSPs and servlets.

    - Authentication and authorization for Web applications:
      Web applications need robust authentication and authorization mechanisms, such as HTTPS. Expert Ramesh Nagappan explains what measures are needed before you deploy Web apps.

    - How to create a secure login page using ASP.NET:
      A secure ASP.NET login page is easier to create than one might assume. Expert Dan Cornell explains how to use authentication, authorization and HTTPS to ensure your login page is safe.






<EOF>
