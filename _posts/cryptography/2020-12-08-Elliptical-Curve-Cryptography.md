This archive is based on: https://searchsecurity.techtarget.com/definition/elliptical-curve-cryptography

--------
Elliptical Curve Cryptography (ECC) is a Public Key encryption technique, which is based on elliptic curve theory, that can be used to create faster, smaller, and more efficient cryptographic keys.

Elliptical Curve Cryptography (ECC) generates keys through the Properties of the Elliptic Curve Equation instead of the traditionsl method of generation as the Product of very large Prime Numbers.

The technology can be used in conjunction (conj.) with most Public Key Encryption methods, such as:
    RSA;
    Diffie-Hellman.

According to some researchers, ECC can yield a level of security with a 164-bit key, that other systems require a 1,024-bit key to achieve.

Because elliptical curve cryptography (ECC) helps to establish equivalent security with lower computing power and battery resource usage, it is becoming widely used for Mobile Applications.

--------
ECC was developed by Certicom, a mobile e-business security provider, and was recently licensed by Hifn, a manufacturer of Integrated Circuiry (IC) and network security products.

RSA jas been developing its own version of ECC.

Many manufactures, including 3COM, Cylink, Motorola, Pitney Bowes, Siemens, TRW, and VeriFone have included support for ECC in their products.

--------
The properties and functions of elliptic curves have been studied in mathematics for 150 years. Their use within cryptography was first proposed in 1985, (separately) by Neal Koblitz from the University of Washington, and Victor Miller at IBM. 

An elliptic curve is not an "ellipse" (oval shape), but is represented as a looping line intersecting two "axes" (lines on a graph used to indicate the position of a point). 

ECC is based on properties of a particular type of equation created from the "mathematical group" (a set of values for which operations can be performed on any two members of the group to produce a third member) derived from points where the line intersects the axes.

Multiplying a point on the curve by a number, will produce another point on the curve. But it is very different to find what number was used, even if you know the original point and the result!

Equations based on elliptic curve have a characteristic that is very valuble for cryptography purpose:
    they are relativly easy to perform, and extremely different to reverse!

--------
The industry still has some reservations about the use of elliptic curves. Nigel Smart, a Hewlett Packard researcher, discovered a flaw in which certain curves are extremely vulnerable, those implementing ECC would have to know which curves could not be used.

He believes that Elliptical Curve Cryptography (ECC) offers a unique potential as a technology that could be implemented worldwide and across all devices. According to Deck (quoted in Wired), "the only way you can achieve that is with elliptic curve."





========
密码学基础2：椭圆曲线密码学原理分析
[web link: https://www.jianshu.com/p/3b810faff3ba]

--------
椭圆曲线在密码学的应用:

ECDH - 
    Elliptic Curve Diffie-Hellman

Elliptical Curve Diffie-Hellman 跟 Diffie–Hellman Key Exchange 类似, 只是不再通过模幂运算, 而是通过素数域下的椭圆曲线的标量乘法来实现:
    - Alice 和 Bob 生成各自的公私钥:
        假设 Alice 的私钥是: d_A , 公钥则为: H_A = d_A * G ;
        Bob 的私钥是: d_B , 公钥则为: H_B = d_B * G ;
        Alice 和 Bob 用的同一个基点 G, 同一个整数有限域, 同一条椭圆曲线.

    - Alice 和 Bob 通过不安全的信道交换公钥 H_A 和 H_B (以及 基点 G)

    - 计算共享密钥 (Secret Key), 就是 S:
        Alice 计算: S = d_A * H_B ;
        Bob 计算: S = d_B * H_A ;
        等式: S = d_A * H_B = d_B * H_A = d_A * d_B * G ;
        对称加密算法 AES 或者 3DES 只需要用到坐标点 S 的一个坐标, 如 x 坐标作为密钥即可.

    - 要想破解密钥就好比 "已知 G，aG，bG 求 a 和 b？";
      当 a 和 b 很大的时候, 破解是很困难的, 这也被称为椭圆曲线的离散对数问题, 即 ECDLP.

--------
ECDHE - 
    Ephemeral Elliptical Curve Diffie-Hellman

Ephemeral Elliptical Curve Diffie-Hellman 与 Elliptical Curve Diffie-Hellman 不同之处在于, ECDHE 的公私钥并不固定, 是每次会话临时生成的.

这样就能具有前向安全性, 实际项目中 ECDHE 也用的更多.

--------
ECDSA - 
    Elliptic Curve Digital Signature Algorithm or ECDSA is a cryptographic algorithm used by Bitcoin to ensure that funds can only be spent by their rightful owners.

Elliptical Curve Digital Signature Algorithm 是 Digital Signature Algothrim (DSA) 算法的变种, 常用于数字签名.
    - Alice 通过椭圆曲线算法生成私钥 d_A , 和公钥 H_A ;
    - Alice 对要签名的消息 (Message) 通过哈希算法 (Hash) 生成摘要 (Digest): z (z 为整数)
    - Alice 用私钥 d_A 对摘要 z 生成签名: (r, s) 是计算出的, 最终的签名对.
    - Bob 通过公钥 H_A 校验签名: 如果 x_P mod n = r , 则签名有效.

Note:
    - ECDSA 中用的子群的阶 n 必须是素数, 否则 k_-1 mod n 可能不存在.
    - 选择 k 的随机数生成器一定要设计好, 不能有漏洞; 
      如果随机数生成不够随机或者可预测, 则可能出现两个相同的随机数, 继而会有两个相同的签名;
      如 r_1 = r_2 , 则根据公式可以计算出 k, 继而就能计算出私钥 d_A 了.


--------
TLS 密钥交换:

TLS 里面加密用的 Cipher Suite 常见的有:
    TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256

意思是:
    - TLS: 协议使用 TLS;
    - ECDHE: 使用 ECDHE 进行密钥交换(i.e. 生成 Secret Key);
    - RSA: 使用 RSA 作为服务验证(i.e. 校验签名);
    - AES_128-GCM: 使用 AES_128_GCM 作为对称加密的算法;
    - SHA256: 用于生成信息的摘要(i.e. 用作 Hash 算法).

关于 TLS 的具体流程分析, 这篇文章 [The Illustrated TLS Connection-Every byte of a TLS connection explained and reproduced] 有详细论述, 强烈推荐.
[web link: https://links.jianshu.com/go?to=https%3A%2F%2Ftls.ulfheim.net%2F]

--------
密钥交换和签名通常有三种方式:
    - RSA
    - ECDHE_RSA
    - ECDHE_ECDSA

区别如下:
    - RSA:
      只用 RSA 算法(i.e. sender/client 通过 public key 加密 message; receiver/server 使用 private key 解密).
      密钥交换(Key Exchange)无需数字签名, 不过由于其没有前向安全性, 已经用的不多.

    - ECDHE_RSA:
      使用 ECDHE 密钥交换, RSA 数字签名, 目前使用比较广泛.
      在 ECDHE 中，客户端和服务端都会生成各自的椭圆曲线密钥对(Key Pair);
      服务端给客户端发送它的椭圆曲线公钥的时候使用RSA证书私钥(Server's RSA private Key)做数字签名;
      客户端使用RSA证书中的公钥(public key of Server's RSA Certificate)校验签名.

    - ECDHE_ECDSA:
      使用 ECDHE 密钥交换, ECDSA 数字签名, 需要使用 ECC 证书.

--------
总结 - 椭圆曲线密码学:
    - 素数域 p 和 子群的阶 n 不能太小, 否则会有破解风险, 建议 256 位以上.

    - 素数域大小 p 和 n 需要满足 p 不等于 h*n , 否则会有风险;
      详见 [Weak Curves In Elliptic Curve Cryptography]
      [web link: https://links.jianshu.com/go?to=https%3A%2F%2Fwstein.org%2Fedu%2F2010%2F414%2Fprojects%2Fnovotney.pdf]

    - ECDSA 的椭圆曲线子群的阶 n 必须是素数, 且随机数生成算法一定要够随机不可预测;
      否则会有泄露私钥的风险, 原理如这篇文章就描述了如何使用随机数碰撞获取私钥恢复以太坊钱包的:
      [web link: https://links.jianshu.com/go?to=https%3A%2F%2Fxz.aliyun.com%2Ft%2F2718]

    - 美国国家安全局曾经推荐使用 secp256r1, 它的曲线方程的系数比 secp256k1 复杂许多;
      然而由于该曲线的设计过程不透明, 在生成曲线参数 a 和 b 中使用的随机算法种子是个很奇怪的数字;
      很早就被怀疑有后门, 在棱镜门后怀疑声更甚; 中本聪在设计比特币的时候也恰好绕过了使用该曲线.
      这里有篇文章 [a-tale-of-two-elliptic-curves] 介绍了这两种曲线:
      [web link: https://links.jianshu.com/go?to=https%3A%2F%2Fwww.johndcook.com%2Fblog%2F2018%2F08%2F21%2Fa-tale-of-two-elliptic-curves%2F]

      棱镜门之后, Daniel J. Bernstein 教授早年设计的 curve25519 曲线大火;
      该曲线系数来源明确, 也已经被越来越多的机构采纳:
      [web link of curve25519: https://links.jianshu.com/go?to=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FCurve25519]






















