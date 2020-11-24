句柄（Handle）:
    一般是指获取另一个对象的方法;
    一个标识符,一个广义的指针;
    具体形式可以是一个整数,一个对象,一个真实的指针;
    目的是建立起与被访问对象之间的惟一的联系.
handle:
    操作,处理,控制;
    作为名词时,指某个中间媒介;
    柄,拉手,把手,提梁;
    通过它可以操作,控制某样东西.

identification - 认证:
    确认声明者的身份;
    认证方式:
        身份证,生物学特征,etc
authorization - 授权:
    资源所有者(拥有资源的所有权限)委派执行者(去执行资源的相关操作),赋予执行者指定范围的资源操作权限
    i.e. 委派权限
    p.s. 资源所有者和执行者不限于自然人,可以是应用程序,机器(e.g. 浏览器)
    互联网应用开发常用的实现方式:
        web server 的 session 机制;
        web server 的 cookie 机制;
        颁发授权令牌(i.e. token)
authentication - 鉴权:
    对声明者所声明的权限进行鉴别
    identification -> authorization -> authentication -> access control(permission)
    先授权,后鉴权(上一个环节:授权)
    鉴别通过,再去拿这个"权"(i.e. permission - 权限)
    鉴权是承上启下的一个环节(下一个环节:权限控制)
access control/permission control - 权限控制
    若执行者对资源的操作在其权限范围内,则允许执行;
    否则,禁止执行.
permission - 权限:
    一般用基于角色的方式来定义权限;
    用角色来封装其可执行的操作的集合.



