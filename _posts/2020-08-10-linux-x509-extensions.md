x.509 Certificates - Critical vs non-critical extensions
web link: http://www.securesenses.net/2013/05/x509-certificates-critical-vs-non.html
i.e. 
Each certificate extension has three attributes - extnID, critical, extnValue
[1] extnID - Extension ID - an OID that specifies the format and definitions of the extension
[2] critical - Critical flag - Boolean value
[3] extnValue - Extension value 
 -----> -----> -----> -----> ----->

[1] Criticality flag specifies whether the information in an extension is important. 
[2] If an application doesn't recognize the extension marked as critical, the certificate cannot be accepted. 
[3] If an extension is not marked as critical (critical value False) it can be ignored by an application.
i.e. View certificate extensions using OpenSSL:
 $ openssl x509 -inform pem -in cert.pem -text -noout

 -----> -----> -----> -----> ----->
My Command:
[1] $ openssl ecparam -genkey -name prime256v1 -noout -out 2ndTIMPrivate.pem
[2] $ openssl ec -in 2ndTIMPrivate.pem -pubout -out 2ndTIMPublic.pem
read EC key
writing EC key
[3] $ openssl req -new -days 365 -nodes -x509 -subj "/CN=nsds6" -key 2ndTIMPrivate.pem -out 2ndTIMPrivate.cert
[4] $ keytool -printcert -file 2ndTIMPrivate.cert
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
[5] $ openssl x509 -inform pem -in 2ndTIMPrivate.cert -text -noout
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number: 11783078406949174562 (0xa385e761b6c7fd22)
    Signature Algorithm: ecdsa-with-SHA256
        Issuer: CN=nsds6
        Validity
            Not Before: Aug 10 07:50:34 2020 GMT
            Not After : Aug 10 07:50:34 2021 GMT
        Subject: CN=nsds6
        Subject Public Key Info:
            Public Key Algorithm: id-ecPublicKey
                Public-Key: (256 bit)
                pub: 
                    04:b0:8a:1f:68:c0:37:47:a5:66:9d:8e:5c:74:da:
                    46:1c:34:de:ff:e1:73:d3:c6:60:43:60:d1:bd:1a:
                    3f:b3:35:6a:c5:05:73:16:0c:51:91:5f:af:37:3f:
                    c4:70:13:09:3f:98:d9:2d:f6:c1:2a:ef:ea:a5:d0:
                    36:ad:20:f3:91
                ASN1 OID: prime256v1
                NIST CURVE: P-256
        X509v3 extensions:
            X509v3 Subject Key Identifier: 
                9A:EA:92:47:4D:05:E2:58:AE:EE:D3:3B:A6:3D:62:DA:BA:74:72:3B
            X509v3 Authority Key Identifier: 
                keyid:9A:EA:92:47:4D:05:E2:58:AE:EE:D3:3B:A6:3D:62:DA:BA:74:72:3B

            X509v3 Basic Constraints: 
                CA:TRUE
    Signature Algorithm: ecdsa-with-SHA256
         30:45:02:20:01:23:ad:fd:ee:d5:c8:1e:a0:b9:32:ea:bb:cc:
         72:19:e6:e1:56:66:31:f7:f1:c6:fa:ee:0a:80:4d:7f:94:73:
         02:21:00:83:28:cf:ed:3f:76:41:7c:ed:bb:65:dd:e4:6c:f5:
         7a:83:e0:a3:9e:aa:b1:01:8a:04:77:15:a7:63:31:58:a5
[6] $ openssl x509 -inform der -in TIMPublic_cert.cer -text -noout
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number:
            50:5d:e2:35:69:91:11:84:af:06:20:06:62:90:d1:87:4a:1e:78:87
    Signature Algorithm: ecdsa-with-SHA256
        Issuer: CN=nsds
        Validity
            Not Before: Feb 28 03:36:51 2020 GMT
            Not After : Jul  1 03:36:51 3019 GMT
        Subject: CN=nsds
        Subject Public Key Info:
            Public Key Algorithm: id-ecPublicKey
                Public-Key: (256 bit)
                pub: 
                    04:45:46:fe:fe:18:90:eb:31:66:ac:11:9b:96:5f:
                    4c:08:fe:c9:1b:cb:2f:d3:75:b0:16:1f:29:c0:bf:
                    b7:26:27:d9:3a:02:d3:87:5e:77:23:d2:5b:72:e1:
                    b1:9d:62:61:6d:d0:60:8c:ef:63:3e:db:ca:23:de:
                    78:25:d6:47:74
                ASN1 OID: prime256v1
                NIST CURVE: P-256
        X509v3 extensions:
            X509v3 Subject Key Identifier: 
                A0:1E:49:3D:14:95:55:D1:1B:5F:6D:A6:72:08:8D:3D:71:50:95:82
            X509v3 Authority Key Identifier: 
                keyid:A0:1E:49:3D:14:95:55:D1:1B:5F:6D:A6:72:08:8D:3D:71:50:95:82

            X509v3 Basic Constraints: critical
                CA:TRUE
    Signature Algorithm: ecdsa-with-SHA256
         30:44:02:20:01:54:5e:30:43:06:44:4d:37:fa:d0:c0:a0:b1:
         df:9b:28:a0:bf:ec:68:44:4d:1a:42:52:a4:87:99:b9:15:98:
         02:20:5e:4c:9a:b8:1a:1d:78:ea:1c:28:97:73:44:82:11:0a:
         dd:6a:d3:d5:9d:98:2b:d8:af:91:23:f2:50:7b:96:08







 =====> =====> =====> =====> =====>

How to generate x509v3 Extensions in the End user certificate:
web link: https://access.redhat.com/solutions/28965
i.e. After signing the cert , check if the extensions are properly added:
 $ openssl x509 -text -noout -in user-certificate.crt



 =====> =====> =====> =====> =====>
Which properties of a X.509 certificate should be critical and which not?
web link: https://security.stackexchange.com/questions/30974/which-properties-of-a-x-509-certificate-should-be-critical-and-which-not
i.e. See the RFC for the details on every extension: these are guidelines for how your CA should behave. For instance, Key Usage is a "SHOULD be critical", Basic Constraints is a "MAY be critical", Name Constraints is a "MUST be critical", and so on... If you follow these rules, your security will be fine (but you may have to make some modifications for interoperability).





 =====> =====> =====> =====> =====>
"critical,CA:FALSE" but "Any Purpose CA : Yes":
web link: http://openssl.6102.n7.nabble.com/quot-critical-CA-FALSE-quot-but-quot-Any-Purpose-CA-Yes-quot-td29933.html

When creating a certificate using an openssl CA, I specify the x509v3 extension basicConstraints = critical,CA:FALSE.

Looking at the generated certificate using:
 $ openssl x509 -noout -text -purpose -in nonca.pem

 -----> -----> -----> -----> -----> 
My command:
$ openssl x509 -noout -text -purpose -in TIMPublic_cert.cer -format der
unknown option -format
usage: x509 args
 -inform arg     - input format - default PEM (one of DER, NET or PEM)
 -outform arg    - output format - default PEM (one of DER, NET or PEM)
 -keyform arg    - private key format - default PEM
 -CAform arg     - CA format - default PEM
 -CAkeyform arg  - CA key format - default PEM
 -in arg         - input file - default stdin
 -out arg        - output file - default stdout
 -passin arg     - private key password source
 -serial         - print serial number value
 -subject_hash   - print subject hash value
 -subject_hash_old   - print old-style (MD5) subject hash value
 -issuer_hash    - print issuer hash value
 -issuer_hash_old    - print old-style (MD5) issuer hash value
 -hash           - synonym for -subject_hash
 -subject        - print subject DN
 -issuer         - print issuer DN
 -email          - print email address(es)
 -startdate      - notBefore field
 -enddate        - notAfter field
 -purpose        - print out certificate purposes
 -dates          - both Before and After dates
 -modulus        - print the RSA key modulus
 -pubkey         - output the public key
 -fingerprint    - print the certificate fingerprint
 -alias          - output certificate alias
 -noout          - no certificate output
 -ocspid         - print OCSP hash values for the subject name and public key
 -ocsp_uri       - print OCSP Responder URL(s)
 -trustout       - output a "trusted" certificate
 -clrtrust       - clear all trusted purposes
 -clrreject      - clear all rejected purposes
 -addtrust arg   - trust certificate for a given purpose
 -addreject arg  - reject certificate for a given purpose
 -setalias arg   - set certificate alias
 -days arg       - How long till expiry of a signed certificate - def 30 days
 -checkend arg   - check whether the cert expires in the next arg seconds
                   exit 1 if so, 0 if not
 -signkey arg    - self sign cert with arg
 -x509toreq      - output a certification request object
 -req            - input is a certificate request, sign and output.
 -CA arg         - set the CA certificate, must be PEM format.
 -CAkey arg      - set the CA key, must be PEM format
                   missing, it is assumed to be in the CA file.
 -CAcreateserial - create serial number file if it does not exist
 -CAserial arg   - serial file
 -set_serial     - serial number to use
 -text           - print the certificate in text form
 -C              - print out C code forms
 -md2/-md5/-sha1/-mdc2 - digest to use
 -extfile        - configuration file with X509V3 extensions to add
 -extensions     - section from config file with X509V3 extensions to add
 -clrext         - delete extensions before signing and input certificate
 -nameopt arg    - various certificate name options
 -engine e       - use engine e, possibly a hardware device.
 -certopt arg    - various certificate text options
 -checkhost host - check certificate matches "host"
 -checkemail email - check certificate matches "email"
 -checkip ipaddr - check certificate matches "ipaddr"


















































