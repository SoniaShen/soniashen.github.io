How To Generate Self Signed X.509 Certificates with OpenSSL
web link: https://www.poftut.com/how-to-generate-self-signed-x-509-certificates-with-openssl/


OpenSSL Basic Constraints
web link: https://security.stackexchange.com/questions/153310/openssl-basic-constraints


Using the Basic Constraints extension in X.509 v3 certificates for intermediate CAs
web link: https://unitstep.net/blog/2009/03/16/using-the-basic-constraints-extension-in-x509-v3-certificates-for-intermediate-cas/










 =====> =====> =====> =====> =====>
How To Create a SSL Certificate on Apache for Ubuntu 14.04
web link: https://www.digitalocean.com/community/tutorials/how-to-create-a-ssl-certificate-on-apache-for-ubuntu-14-04
[1] Activate the SSL Module
[2] Create a Self-Signed SSL Certificate
-x509: This option specifies that we want to make a self-signed certificate file instead of generating a certificate request.
[3] Configure Apache to Use SSL
[4] Activate the SSL Virtual Host
[5] Test your Setup







openssl ecdsa - openssl ecdsa
web link: https://wiki.openssl.org/index.php/Command_Line_Elliptic_Curve_Operations
i.e. OpenSSL provides two command line tools for working with keys suitable for Elliptic Curve (EC) algorithms:
[1] openssl ecparam
[2] openssl eC

EC Public Key File Formats:
It is possible to create a public key file from a private key file (although obviously not the other way around!):
 $ openssl ec -in ecprivkey.pem -pubout -out ecpubkey.pem






 =====> =====> =====> =====> =====>
Creating ECDSA SSL Certificates in 3 Easy Steps:
web link: https://zonena.me/2016/02/creating-ssl-certificates-in-3-easy-steps/
i.e. Self-Signed Certificate
[1] If you want a self signed certificate instead, run this:
 $ openssl x509 -req -sha256 -days 365 -in server.csr -signkey private.key -out public.crt

[2] You can also create a self-signed ECDSA certificate in two steps.
 $ openssl ecparam -out www.example.com.key -name prime256v1 -genkey
 $ openssl req -new -days 365 -nodes -x509 \
    -subj "/C=US/ST=Denial/L=Springfield/O=Dis/CN=www.example.com" \
    -key www.example.com.key -out www.example.com.cert 

 -----> -----> -----> -----> -----> 

My Commands:
 $ openssl req -new -days 365 -nodes -x509 -subj "/CN=nsds6" -key 2ndTIMPrivate.pem -out 2ndTIMPrivate.cert
-outform PEM
-outform DER

Check my Cert:
 $ keytool -printcert -file 2ndTIMPrivate.cert
Owner: CN=nsds6
Issuer: CN=nsds6
Serial number: a385e761b6c7fd22
Valid from: Mon Aug 10 15:50:34 CST 2020 until: Tue Aug 10 15:50:34 CST 2021
Certificate fingerprints:
	 MD5:  53:3D:9A:D8:2A:61:C8:CB:E8:42:70:E5:6F:C0:F3:8D
	 SHA1: 8A:80:D0:6E:0E:76:56:A1:05:DD:6C:72:5E:3E:11:22:8E:1E:C8:EF
	 SHA256: D4:89:C4:CF:E0:1A:01:9B:B2:58:48:C7:F1:64:99:6E:CC:62:BF:70:B3:8F:B1:65:79:2A:0C:83:8A:C8:BE:8B
Signature algorithm name: SHA256withECDSA
Subject Public Key Algorithm: 256-bit EC key
Version: 3

Extensions: 

#1: ObjectId: 2.5.29.35 Criticality=false
AuthorityKeyIdentifier [
KeyIdentifier [
0000: 9A EA 92 47 4D 05 E2 58   AE EE D3 3B A6 3D 62 DA  ...GM..X...;.=b.
0010: BA 74 72 3B                                        .tr;
]
]

#2: ObjectId: 2.5.29.19 Criticality=false
BasicConstraints:[
  CA:true
  PathLen:2147483647
]

#3: ObjectId: 2.5.29.14 Criticality=false
SubjectKeyIdentifier [
KeyIdentifier [
0000: 9A EA 92 47 4D 05 E2 58   AE EE D3 3B A6 3D 62 DA  ...GM..X...;.=b.
0010: BA 74 72 3B                                        .tr;
]
]
 <===== <===== <===== <===== <=====










