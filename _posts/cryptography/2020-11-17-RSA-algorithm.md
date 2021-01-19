This archive is based on web link: https://searchsecurity.techtarget.com/definition/RSA

The RSA algrothm is the basis of a crypotosystem -- a suite of cyptographic algrothms that are used for specific security services or purposes -- which enables public key encryprtion and is widely used to secure sensitive data, particularly when it is being sent over an insecure network such as internet.

--------
Public Key cryptography, as know as asymmetric cryptography, uses two different but mathmatically linked keys -- one public and one private.  The public key can be shared with everyone, whereas the private key must be kept secret.

In RSA cryptography, both the public and the private keys can encrypt a message; the opposite key from the one used to encrypt a message is used to decrypt it.

Many protocols like secure shell, OpenPGP, S/MIME, and SSL/TLS rely on RSA for encrytion and digital signature functions. It is also used in software programs -- browsers are an obvious example, as they need to establish a secure connection over an insecure network, like internet, or validate a digital signature. RSA signature verification is one of the most commonly performed operations in network-connected systems.

--------
RSA derives its security from the difficulty of factoring large integers that are the product of two large primw numbers. Multiplying these two numbers is easy, but determining the original prime numbers from the total -- or factoring -- is considered infeasible due to the time it would take using even today's supercomputers.

The public and private key generation algorithm is the most complex part of RSA cryptography. Two large prime numbers, p and q, are generated using the Rabin-Miller primality test algorithm.
[Primality Test, see web link: https://www.geeksforgeeks.org/primality-test-set-3-miller-rabin/]

A modulus, n, is calculated by multiplying p and q. This number is used by both the public and private keys and provides the link between them. Its length, usually expressd in bits, it called the key length.
[ n = pq, phi(n) = (p-1)(q-1) ] --> Let p and q be distinct primes. The Euler Function φ(pq) = (p-1)(q-1)
[http://www.math.unl.edu/~tmarley1/math189/notes/Nov20notes.pdf]
    If p is a prime number, then eulerPhi(p) = (p=1);
    eulerPhi(pq) = phi(p)phi(q)
    eulerPhi(pq) = (p-1)(q-1)

The public key consists of the modulus, n, and a public exponent, e, which is noromally set at 65537, as it's a prime number that is not too large. If you are using openssl to generate RSA public key, e is always set as 65537.

The e figure dosen't have to be a secretly selected prime number, as the public key is shared with everyone.
[ gcd(e, phi(n)) = 1 ] --> Greatest Common Divisor/Greastest Common Factor
[Which means e and eulerPhi(n) are co-primes.]

The private key consists of the modulus, n, and a private/secret exponent, d, which is calculated using the Extended Euclidean algorithm to find the multiplicative inverse with respect to the totient of n.
[ ed mod phi(n) = 1 ] --> [ ed -1 = k * phi(n), k>=1 ] --> [ ed + k*phi(n) = 1, k<1 ] --> [ ax + by = 1 ]
[Extended Euclidean algrithm, see web link: https://en.m.wikipedia.org/wiki/Extended_Euclidean_algorithm#:~:text=Extended%20Euclidean%20algorithm%20also%20refers%20to%20a%20very,useful%20when%20a%20and%20b%20are%20coprime%20.]
[ ax + by = gcd(a,b) ] --> extended Euclidean algorithm

If encrypt the plaintext message m with RSA public key: ciphertext c = RsaPublic(m) = (m)e mod n
Then should decrypt the ciphertext with RSA private key: m = RsaPrivate(c) = (c)d mod n
Message length: 0 <= m < n

    RsaPrivate(RsaPublic(m)) = m
        Which used as: 
        Server generates a pair of RSA keys; 
        client use public key to encrypt the message and send it to server; 
        only server who has the private key can decrypt it.

    RsaPublic(RsaPrivate(m)) = m
        Which used as:
        Server generates a pair of RSA keys;
        server use its private to encrypt the signature and send it to client;
        client will user server's public key to decrypt the signature data.

--------
Example 1: Client use RSA public key to encrypt a message and send it to server
You have generated a pair of RSA keys by selscting two primes: p=13 and q=15
The modulus is: n=13*15=195
The totirnt is: phi(n)=12*14=168 -> Euler's totient function

Then you chooses public key exponent: e=17
Calculate private/secret key exponent using the Extented Euclidean algorithm, which gives: d=89
    ed mod phi(n) = 1 --> ed -1 = k*phi(n), k>=1 --> ed + k*phi(n) = 1, k<1 --> ax + by = 1 = gcd(a,b)
    17d mod 168 = 1
    17d + 168y = 1
    d = 89, k = -9

[Modular arithmetic and GCD, see web link: http://math.cmu.edu/~cargue/arml/archive/13-14/number-theory-09-22-13.pdf]

Now you have RSA public key (n, e) = (195, 17) and RSA private key (n, d) = (195, 89)
 
The plaintext message, m, as number: m=16
Encrypt it into ciphertext, c, using public key (195 ,17), then: 
    c = 16(17) mod 195 = 61

Decrypt the ciphertext back into original plaintext by using the private key(195, 89), as: 
    m = (61)89 mod 195 = 16

--------
Example 2: Server use RSA private key to digitally sign a message - Encrypt the hash value
Hash --> A message digist of the message
Digital Signature --> encrypt the hash with the private key, along with other information, such as the hashing algorithm, etc.

[About digital signature, see web link: https://searchsecurity.techtarget.com/definition/digital-signature
and arichve: 2020-11-24-digital-signature.md]

To use RSA private to digitally sign a message, you should create a one-way hash of the message, and then encrypt the hash value with the private key. Now you have a digital signature and add it to the message.

After client receive the message along with the sigature, client can then verify that the message has been sent by server and has not been alerted, by decrypting the signature using the public key. Hash the message and compare with decrypted signature, if matches then only the server who generate this RSA key pair could have sent it, which shows authentication and non-repudiation. And the message is exactly as she wrote it, which shows integrity.

--------
Example 3: Encrypt the message with client's public key, then encrypt the message hash with server's private key as signature.
Which shows confidenticality.

A digital certificate contains information that identifies the certificate's owner, and also contains the owner's public key.
[About Digital Certificate, see web link: https://searchsecurity.techtarget.com/definition/digital-certificate]

Certificates are signed by the certificate authority that issues them, which can simplify the process of obtaining public keys and verifying the owner.
[About Certificate Authority, see web link: https://searchsecurity.techtarget.com/definition/certificate-authority]

--------
RSA security relies on the computatuinal difficulty of factoring large integers. As computing power increase and more efficient factoring algorithm are discovered, the ability to factor larger and larger numbers also increases.

Encryption strength is directly tied to key size, and doubling key length can deliver an exponential increase in strength, although it does impair/destory performance. RSA keys are typitally 1024-bits or 2048-bits long, but experts believe that 1024-bits keys are no longger fully secure against all attack. This is why government and some industries are moving to a minimum key length of 2048-bits.

--------
Barring an unforseen breakthrough in quantum computing, it will be many years before longer keys are required, but Elliptic Curve Cryptography (ECC) is gaining favor with many security experts as an alternative to RSA to implement public key cryptographic keys.
[About ECC, see web link: https://searchsecurity.techtarget.com/definition/elliptical-curve-cryptography]
 
Modern hardware and software are ECC-ready, and its popularity is likely to grow, as it can deliver equivalent security with lower computing power and battery resource usage, making it more suitable for mobile apps than RSA.



===============================================





[密码学基础1：RSA算法原理全面解析
web link: https://www.jianshu.com/p/6aa7b59be872
Strongly suggested as the explination and description are very specific.]

--------
[知识点]费马数
对于e，通常可选 3, 5, 17, 257 和 65537。因为它们都是质数，且二进制中只有2位是1，可以加快 d 的计算。这几个e的可选值实际是费马数的前5个数,从 F0 到 F4 都是质数，但是从 F5 开始就不是质数了。实际应用中通常选择 F4=65537 作为 e。

--------
[知识点] 大质数生成算法
如何生成这两个大质数，这是个值得研究的问题。首先可以想到的是生成质数序列，从中随机选取2个大质数即可。
一种改进的方法是: 
    除了 2 外的偶数肯定不是质数，而奇数可能是质数，可能不是，那就可以跳过2与3的倍数，即对于 6n，6n+1, 6n+2, 6n+3, 6n+4, 6n+5，我们只需要判断 6n+1 与 6n+5 是否是质数即可。
    而判断某个数m是否是质数，最基本的方法就是对 2 到 m-1 之间的数除 m，如果有一个数能够整除 m，则 m 就不是质数。
    判断 m 是否是质数还可以进一步改进，只需要对 2 到 根号m 之间的数除 m 就可以。
    继续优化，其实只用 2 到 根号m 之间的质数去除即可。

上面生成大质数是很基础的方法，效率比较低，一般会采用更快的方式，比如随机生成一个 n-bits 位的奇数 p，然后从 p 开始遍历之后的奇数，并通过 Miller–Rabin 质数判定算法对遍历到的数字进行质数判定，如果是质数，即可返回(当然，该算法有一定的误判率，不过在判定次数设置够大的情况下，误判率基本可以忽略)。

--------
如何破解 RSA：
大整数的质数因式分解还是比较难的。虽然除了暴力破解外，还有一些效率比较高的整数因式分解方法，如 二次筛分算法 和 普通数域筛选法（GNFS） 等，当你的RSA密钥位数在4096位以上，使用常规运算能力的电脑还是较难破解的。当然不排除某一天，数论研究出现了新的成果，若有一种通项公式可以分解大整数的话，那现有基于 RSA 的加密体系都会崩塌。此外，RSA 加密用的 e 不能太小，否则有潜在的风险，实际应用中常用 65537。

如果已知 N，e，d，则可以很高效地对 N 实现因式分解，得出 p 和 q，原理就不赘述了，实现代码见 factor.py

在实际应用如HTTPS中，RSA 密钥因为性能原因以及没有前向安全性，通常并不直接用来加密数据，
而是只用于在密钥交换时用于签名以认证身份，加密通常会基于 ECDHE 等算法协商一个密钥，然后再基于对称加密算法如 AES 等对数据加密传输。

--------
RSA 密钥格式实例分析：
使用 openssl 工具生成一对 RSA 密钥，示例的私钥文件取名 rsa_demo.key；公钥文件取名 rsa_demo.pub
    # openssl genrsa -out rsa_demo.key 2048
    # openssl rsa -in rsa_demo.key -pubout -out rsa_demo.pub

最常用的 RSA 密钥的模式是 PKCS#1 中规定的模式，即公钥包括 N, e，而私钥包括 N, e, d, p, q, dP, dQ, qInv。

查看公私钥文件内容，可以看到采用的是 DER(Distinguished Encoding Rules) 编码的。
公钥解码后，得到：
    # grep -v '\-\-\-\-\-' rsa_demo.pub | tr -d '\n' | base64 -D | hexdump
        0000000 30 82 01 22 30 0d 06 09 2a 86 48 86 f7 0d 01 01
        0000010 01 05 00 03 82 01 0f 00 30 82 01 0a 02 82 01 01
        0000020 00 bd e4 43 1a d0 02 1e e6 12 34 14 91 84 4d 65
        ......
        0000120 b1 02 03 01 00 01                              
        0000126

DER 编码是一种type-length-value编码，即包括：对象类型，数据长度域，数据域。

示例的 RSA 公钥中， 0x30 是 Sequence 类型，0x03 是 Bit String 类型，而 0x02 是 Integer 类型，0x04是字符串类型，0x06是 Object ID 类型，0x05 00表示NULL。长度如果>=128，则会先跟一个 0x81 或 0x82。0x81表示后面一个字节为长度，0x82表示后面两个字节为长度。然后是数据长度的值，没超过则就是长度值。
整个结构是一个嵌套结构，公钥的 n 和 e 两个数值位于 BIT STRING 这块数据中，可以分析知道从 00000020 开始的 00bde4...b1 是 n，而从 0000123 开始的 010001 是 e，即 65537。
另外，Object ID 是标识密钥的元信息的地方，对应的是 2a 86 48 86 f7 0d 01 01 01 这 9 个字节，这个代表什么含义呢？其实转义过来是 1.2.840.113549.1.1.1，这个 OID 表示的是 RSA 加密系统的公钥。私钥格式类似。

--------
如果不想了解公私钥的格式，直接通过 openssl 的工具即可解析出公私钥的内容，容易验证，这些值正是基于前面的 RSA 原理计算得来的。

    # openssl rsa -in rsa_demo.key -noout -text
        Private-Key: (2048 bit)
        modulus: # N
            00:bd:e4:43:1a:d0:02:1e:e6:12:34:14:91:84:4d:
            ...
        publicExponent: 65537 (0x10001) # e
        privateExponent: # d
            76:bb:8d:41:ec:a2:06:d3:f0:b9:e3:ca:81:21:2b:
            ...
        prime1: # p
            00:fa:99:34:b8:b3:97:dc:09:37:29:dd:df:de:86:
            ...
        prime2: # q
            00:c1:fc:13:f7:84:dd:f4:b5:05:2d:89:b9:a1:50:
            ...
        exponent1: # dP
            00:c9:7d:61:cc:98:6a:23:bb:2d:25:76:86:47:cf:
            ...
        exponent2: # dQ
            00:99:e8:43:7b:45:ea:c8:45:7b:57:37:07:95:ea:
            ...
        coefficient: # qInv
            0c:53:5f:0c:a6:7b:33:69:32:b6:b9:65:f8:31:5f:
            ...
    
    # openssl rsa -pubin -in rsa_demo.pub -noout -text
        Public-Key: (2048 bit)
        Modulus: # N
            00:bd:e4:43:1a:d0:02:1e:e6:12:34:14:91:84:4d:
            ...
        Exponent: 65537 (0x10001) # e

--------
[About dP, dQ, qInv,see 图解PKCS#1, web link: https://blog.csdn.net/samsho2/article/details/84255382
PKCS #1 v2.2: RSA Cryptography Standard:
web link: https://www2.karlin.mff.cuni.cz/~kozlik/ks_2017/pkcs1.pdf]









