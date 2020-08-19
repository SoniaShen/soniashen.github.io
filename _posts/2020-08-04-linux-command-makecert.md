The program 'makecert' is currently not installed. You can install it by typing:
sudo apt install mono-devel

[1] MakeCert - Create X.509 certificates for test purposes:
web link: https://www.systutorials.com/docs/linux/man/1-makecert/    [VPN needed]
web link: https://linux.die.net/man/1/makecert    [suggested]

[2] makecert(1) - Linux man page:
web link: https://linux.die.net/man/1/makecert    [VPN needed]

[3] openssl的x509命令简单入门:
web link: https://blog.csdn.net/u010846177/article/details/54356897

[4] HowTo: Create self-signed certificates with MakeCert
web link: https://www.virtues.it/2015/08/howto-create-selfsigned-certificates-with-makecert/



 =====> =====> =====> =====> =====>
Makecert, X509 Certificates and RSA:
web link: https://nick-howard.blogspot.com/2011/05/makecert-x509-certificates-and-rsa.html    [vpn]
[focus on using all the bits together to do X509 certificate key based RSA provider encryption and decryption using C#]


Creating self signed certificates with makecert.exe for development:
web link: https://blog.jayway.com/2014/09/03/creating-self-signed-certificates-with-makecert-exe-for-development/
i.e. makecert.exe ^
-n "CN=CARoot" ^
-r ^
-pe ^
-a sha512 ^
-len 4096 ^
-cy authority ^
-sv CARoot.pvk ^
CARoot.cer

-n “CN=CARoot” ➜ Subject’s certificate name and must be formatted as the standard: “CN=Your CA Name Here”
You can also add more than one in the -n parameter for example: “-n “CA=CARoot,O=My Organization,OU=Dev,C=Denmark”  and so on. Reference:
CN = commonName (for example, “CN=My Root CA”)
OU = organizationalUnitName (for example, “OU=Dev”)
O = organizationName (for example, “O=Jayway”)
L = localityName (for example, “L=San Francisco”)
S = stateOrProvinceName (for example, “S=CA”)
C = countryName (for example, “C=US”)
-r ➜ Indicates that this certificate is self signed
-pe ➜ The generated private key is exportable and can be included in the certificate
-a sha512 ➜ We declare which signature algorithm we will be using
(DO NOT use the sha1 algoritm, it is no longer secure)
-len 4096 ➜ The generated key length in bits
-cy authority ➜ Specifies that this is a certificate authority
-sv CARoot.pvk ➜ The subject’s .pvk private key file
CARoot.cer ➜ The certificate file

 -----> -----> -----> -----> ----->
my command:
makecert -n "CN=nsds2" -r -a sha512  -cy authority CARoot.cer

keytool -printcert -file CARoot.cer 
Owner: CN=nsds2
Issuer: CN=nsds2
Serial number: 3b4516cfebe64241b58623112ffe083c
Valid from: Mon Aug 10 09:21:19 CST 2020 until: Sat Dec 31 18:59:59 CST 2039
Certificate fingerprints:
	 MD5:  28:DC:8A:05:CC:AF:DA:76:84:83:C2:37:3A:22:98:5E
	 SHA1: BD:68:DE:2D:7E:DA:71:CE:0E:9B:29:BC:01:32:24:D2:09:77:F7:01
	 SHA256: A5:03:7B:FB:0C:F1:A4:1C:A1:BA:3C:1D:68:A7:AF:42:E2:7B:CE:D3:F0:F1:39:37:1C:8A:A7:70:C3:40:C5:F4
Signature algorithm name: SHA1withRSA
Subject Public Key Algorithm: 1024-bit RSA key
Version: 3

Extensions: 

#1: ObjectId: 2.5.29.19 Criticality=false
BasicConstraints:[
  CA:true
  PathLen:2147483647
]

 -----> -----> -----> -----> ----->
Mac created TIMPublic_cert.cer:
keytool -printcert -file TIMPublic_cert.cer
Owner: CN=nsds
Issuer: CN=nsds
Serial number: 505de23569911184af0620066290d1874a1e7887
Valid from: Fri Feb 28 03:36:51 UTC 2020 until: Thu Jul 01 03:36:51 UTC 3019
Certificate fingerprints:
         MD5:  CF:5B:BB:48:98:AB:A3:5F:B3:1F:E4:72:E8:B5:C2:12
         SHA1: 63:CD:A0:4F:A4:43:90:32:C5:78:5D:BD:A1:E9:5D:B4:6B:A1:EB:FB
         SHA256: E1:CF:5E:C6:D1:78:8E:41:C5:3E:47:6A:0F:21:5A:1F:1A:BE:CC:57:55:7D:AF:F3:00:3B:45:F3:28:EB:EB:EF
Signature algorithm name: SHA256withECDSA
Subject Public Key Algorithm: 256-bit EC key
Version: 3

Extensions:

#1: ObjectId: 2.5.29.35 Criticality=false
AuthorityKeyIdentifier [
KeyIdentifier [
0000: A0 1E 49 3D 14 95 55 D1   1B 5F 6D A6 72 08 8D 3D  ..I=..U.._m.r..=
0010: 71 50 95 82                                        qP..
]
]

#2: ObjectId: 2.5.29.19 Criticality=true
BasicConstraints:[
  CA:true
  PathLen:2147483647
]

#3: ObjectId: 2.5.29.14 Criticality=false
SubjectKeyIdentifier [
KeyIdentifier [
0000: A0 1E 49 3D 14 95 55 D1   1B 5F 6D A6 72 08 8D 3D  ..I=..U.._m.r..=
0010: 71 50 95 82                                        qP..
]
]

 <===== <===== <===== <===== <=====

-sv pkvfile
Specify the private key file (.PVK) for the subject. The public part of the key will be inserted into the created certificate. If non-existant the specified file will be created with a new key pair (default to 1024 bits RSA key pair).

Difference:
[1] Subject Public Key Algorithm: 1024-bit RSA key
[2] Subject Public Key Algorithm: 256-bit EC key













Setting Key Usage attributes with Makecert
web link: https://stackoverflow.com/questions/2955049/setting-key-usage-attributes-with-makecert    [vpn
i.e. MakeCert doesn't let you specify key usage, only extended key usage. I think you need a CA to create a broader certificate. You can setup your own CA with ubuntu server. https://www.digitalocean.com/community/tutorials/how-to-create-a-ssl-certificate-on-apache-for-ubuntu-14-04


Using MakeCert
web link: https://docs.microsoft.com/en-us/windows/win32/seccrypto/using-makecert











































