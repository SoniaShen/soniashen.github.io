Socket API, Servlet API, Websocket API

socket - 网络传输中的一端(translate: 插座)
    建立网络通信连接至少要一对端口号;
    用于描述 IP Address 和 Port;是一个通信链的 Handle;
    每种服务都开一个 Socket(i.e. 绑定到一个 Port 上), Different Ports for Different Services.

[web link: https://www.jianshu.com/p/59b5594ffbb0]
    Socket可以有很多意思,和 IT 较相关的本意大致是指:
        在端到端的一个连接中, 这两个端叫做Socket!
        往往指的是TCP/IP网络环境中的两个连接端!
        Socket API 则是基于这种编程概念(SOCKET)的接口!
    P.S. 
        Unix操作系统中,进程间通信,也有Socket的概念;
        此时的Socket就不基于网络传输层的协议TCP/IP了;
        而是基于操作系统本身的 文件系统.

servlet - server applet(i.e. A very small application/utility program performing a few simple functions)
    Servlet - A small, server-resident program that typically runs AUTOMATICALLY in response to user input.
    从原理上讲, Servlet 可以响应任何类型的请求;
    大多数情况下, Servlet 用于扩展基于HTTP协议的Web服务器:
        1) Client 发送请求至 Server;
        2) Server 将请求发至 Servlet;
        3) Servlet 生成响应内容并将其传给 Server (响应内容动态生成, 取决于 Client 的请求);
        4) Server 将响应返回给 Client;

websocket 协议 - HTTP 1.1 协议诞生于1999年, websocket 协议议诞生于2011年.
    [Socket一直以来被人用来表示网络中一个连接的两端]
    本协议的目的是:
        为了解决基于浏览器(Browser)的程序需要拉取资源时, 必须发起多个HTTP请求 & 长时间的轮训的问题, 而创建的.
    P.S. 
        WebSocket通信协议于2011年被IETF定为标准RFC 6455，并由RFC7936补充规范。WebSocket API也被W3C定为标准。

    WebSocket API:
        浏览器(Browser) 和 服务器(Server) 只需要做一个握手的(Handshake)动作;
        然后 Browser 和 Server 之间就形成了一条快速通道;
        两者之间直接可以互相传送数据.
    WebSocket 协议为我们实现 即时服务 带来了 2 大好处:
        1) Header - 互相沟通的 Header 很小, 约 2Byets
        2) Server Push - 服务器推送;
            Server 将不再是被动的, 接收到 Browser 的request之后才返回数据;
            而是, 在有新数据时, 主动推送给 Browser.


WebSocket：实现http双向通信:
web link: https://www.jianshu.com/p/ccce3504e1e6

通过HTTP请求Websocket:
web link: https://blog.csdn.net/zt102545/article/details/85396360

HTTP之TCP三次握手及四次挥手详解
web link: https://www.jianshu.com/p/12790cea57ac

JAX-RS即Java API for RESTful Web Services:
web link: https://baike.baidu.com/item/JAX-RS/10914743




