web link: https://devcentral.f5.com/s/articles/building-an-openssl-certificate-authority-creating-your-root-certificate-27721

i.e.
  Country Name (2 letter code) [US]:
  State or Province Name [WA]:
  Locality Name [Seattle]:
  Organization Name [Grilled Cheese Inc.]:
  Organizational Unit Name [Grilled Cheese Root CA]:
  Common Name []:Grilled Cheese Root Certificate Authority
  Email Address [grilledcheese@yummyinmytummy.us]:


 =====> =====> =====> =====> =====>
File Location:
    /etc/ssl/openssl.cnf

####################################################################
[ req ]
default_bits            = 2048
default_keyfile         = privkey.pem
distinguished_name      = req_distinguished_name
attributes              = req_attributes
x509_extensions = v3_ca # The extentions to add to the self signed cert


####################################################################
[ v3_ca ]
# Extensions for a typical CA
# PKIX recommendation.

subjectKeyIdentifier=hash
authorityKeyIdentifier=keyid:always,issuer

# This is what PKIX recommends but some broken software chokes on critical
# extensions.
#basicConstraints = critical,CA:true
# So we do this instead.
basicConstraints = CA:true








