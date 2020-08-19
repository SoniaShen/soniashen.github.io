ec(1) - Linux man page:
web link: https://linux.die.net/man/1/ec


Generate EC KeyPair from OpenSSL command line
web link: https://stackoverflow.com/questions/15686821/generate-ec-keypair-from-openssl-command-line    [vpn]
 =====> =====> =====> =====> =====>
Private Key
Assuming an UX platform such as OS X or Linux. Also omit the $ when testing. Generate a private ECDSA key:
 $ openssl ecparam -name prime256v1 -genkey -noout -out private.ec.key

Convert and encrypt the private key with a pass phrase:
 $ openssl pkcs8 -topk8 -in private.ec.key -out private.pem
You can now securely delete private.ec.key as long as you remember the pass phrase.

Public Key
Generate public ECDSA key:
 $ openssl ec -in private.pem -pubout -out public.pem

TBC...
 <===== <===== <===== <===== <===== 


256-bit EC key >>> ECDSA algorithm
SHA256withECDSA >>> ES256 (https://jwt.io/) 








How to restrict what certificates and algorithms clients can use to connect to java web servers:
WEB LINK: https://colinpaice.blog/2020/04/12/how-to-restrict-what-certificates-and-algorithms-clients-can-use-to-connect-to-java-web-servers/
i.e. 
For example RSA4096,SHA256withECDSA,/EC256,SHA384with ECDSA means

[1] RSA4096 certificate is RSA with a key size of 4096
[2] SHA256withECDSA signed with this
[3] /EC256 the CA has a public key of EC 256
[4] SHA384with ECDSA and the CA was signed with this






How to create a digital signature using SHA256 with ECDSA algorithm in C#
web link: https://stackoverflow.com/questions/32692748/how-to-create-a-digital-signature-using-sha256-with-ecdsa-algorithm-in-c-sharp    [vpn]
i.e. 
Unlike RSA PKCS#1 v1.5 signatures, ECDSA signatures are not deterministic. In other words, they depend on a random number generator to generate the signatures. The signatures will have a different value after each signing operation. The correctness of the value of these signatures can only be tested by verifying with the public key.





Command Line Elliptic Curve Operations:
web link: https://wiki.openssl.org/index.php/Command_Line_Elliptic_Curve_Operations
i.e. 
By default OpenSSL will work with PEM files for storing EC private keys.
You may also encounter PKCS8 format private keys in PEM files. 
PKCS8 private key files, like the above, are capable of holding many different types of private key - not just EC keys.
To convert a PKCS8 file to a traditional unencrypted EC format, just drop the first argument:
Or to convert from a traditional EC format to an encrypted PKCS8 format use:
Or to a non-encrypted PKCS8 format use:





How to generate RSA and EC keys with OpenSSL:
web link: https://connect2id.com/products/nimbus-jose-jwt/openssl-key-generation
i.e. 
Elliptic Curve keys
To generate an EC key pair the curve designation must be specified. Note that JOSE ESxxx signatures require P-256, P-384 and P-521 curves (see their corresponding OpenSSL identifiers below).

[1] Elliptic Curve private + public key pair for use with ES256 signatures:
 $ openssl ecparam -genkey -name prime256v1 -noout -out ec256-key-pair.pem











