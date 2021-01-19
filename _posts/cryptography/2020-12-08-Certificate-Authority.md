This archive is based on: https://searchsecurity.techtarget.com/definition/certificate-authority

--------
A Certificate Authority (CA) is a trusted entity that issues Digital Certificates, which are data files used to cryptographically link an Entity with a Public Key. Certificate authorities are a critical part of the Internet's Public Key Infranstructure (PKI), because they issue the Secure Socket Layer (SSL) certificates (i.e. SSL Certificates, AKA, digital certificates that web browsers use to authenticate content sent from web servers.

--------
All major web browsers use web servers' SSL certificate to maintain trust in content delivered online; they all must trust the Certificate Authorities (CA) to issue certificates reliably. SSL Certificates are used with the Transport Layer Security (TLS) protocol to encrypt and authenticate data streams for the HTTPS protocol, and are sometimes referred to as SSL/TLS certificates (or, simply, TLS certificates).

========
[About SSL certificates: https://searchsecurity.techtarget.com/definition/SSL-certificate-Secure-Sockets-Layer-certificate]

Secure Sockets Layer certificate:

A Secure Sockets Layer certificate (SSL Certificate) is a small data file installed in a Web Server that allows for a secure connection between the server and a Web Browser.

SSL certificates can be used by online enterprises wishing to encrypt Credit Card Transactions, make Data Transfers, Process Logins, and Host Secure Social Media Websites.

Based on the Secure Sockets Layer protocol developed bt Netscape, SSL certificates use a cryptographic key to provide validation for a Web Server, detailing its Domain Name, Server Name, Hostname, Company Name, and Location. Most SSL certifivates today also support the Transport Layer Security (TLS) protocol, which is considered to be more secure that SSL.

SSL certificates are issued from a trusted Certificate Authority (CA). There are three types of certificates:
    - Extended Validation (EV) SSL certificates;
    - Organization Validation (OV) SSL certificates;
    - Domain Validation (DV) SSL certificates.

When an SSL certificate is installed on a Web Server, it activates the HTTPS protocol over port 443.
The use of an SSL certificate on a Website is usually indicated by a padlock icon and a URL that begins with https://.
========

Continue with the CA part...

Digital certificates contains data about the entity that issued the certificate along with cryptography data tat can be used to verify the identity of the entity linked to the Digital Certificate.

Typically, a Digital Certificate will contain information about the entity to which it has been issued, including the entity's public key, and expiration data for the certificate, as well the entity's name, contact information and other information linked to the certified entity.

--------
Web Servers transmit this information when a Web Browser initiates a secure connection over HTTPS; the certificate is sent to the web Browser, which authenticates the certificate against its own root certificate store.

Root Certificate Store:
The major browser companies -- Microsoft, Google, Apple, and Mozilla -- each maintain their own web browser root certificate stores, in which they post the root certificates of the certificate authorities (CAs), which the publisher has decided their browser will trust.

--------
An entity or person who needs a Digital Certificate can requset one from a CA; once the certificate authoritises verifies the applicant's identity, it generates a Digital Certificate for the applicant and digitally signs that certificate with the certificate authority's (CA's) private key.

The digital certificate can then be authenticated (for example, by a web browser) using the certificate authority's (CA's) public key.

--------
The certificate authority's Root Certificate should never be used directly for signing digital certificates, but rather is used to generate intermediate certificates as needed; different intermediate certificates are generated for different purposes.

For example, a CA provider may be use:
    - an intermediate certificate to sign all Digital Certificates generated for different levels of trust;
    - or a seperate intermediate certificate to be used for all Digital Certificates generated for a particular customer organization.

--------
Certificate Authorities may accept requsets from applications directly, though they often delegate the task of authenticating applicants to Registration Authorities (RAs).

A Registration Authority is often used for marketing and customer support:
    - The RA collects and authenticates Digital Certificate Requsets,
    - and then submits those requests to the Certificate Authority (CA),
    - (CA) which then issues the certificate to be passed through the RA to the appliant.

--------
Uses of a certificate authority (CA):

The best-known use of certificate authorities is for issuing SSL certificates to entities that publish content on the Web.

CAs issue three levels of SSL certificate, corresponding to different levels of trust in those certificates. Certificates with higher level of trust usually cost more, because they require more work on the part of the certificate authority.

--------
The three different levels of trusted certificates include:

- EV SSL certificates:
 
EV SSL certificates provides highest level of assurance that the CA has validated the entity requesting the certificate.
The Certificate Authority Browser Forum (CA/Browser Forum) spells out details requirements for the process that certificate authorities (CAs) must apply when verifying information provided by the applicant for an EV certificate.
For example, an individual requesting an EV certificate must be validated through face-to-face interaction with the applicant as well as review of a personal statement, one primary form of identification such as passport, driver's license or military ID, as well as two secondary forms of identification. 

- OV SSL certificates:

OV SSL certificates provide the next highest level of assurance.
Certificate Authorities (CAs) generally perform some level vetting of the applicants, which may include telephone verification as well as use of external or third parties to confirm information submitted by the applicant.
OV SSL certificates can be issued if the applicant cab demonstate that it holds administrative control of the Domain Name for which the certificate is requested, and that the organization can be shown to exist as a legal entity.

- DV SSL certificates:

DV SSL certificates require only that the applicant demonstrate ownership of the Domain for which the certificate is being requested.
DV SSL certificates can be acquired almost instantly, and at a low or no cost.
For example, Let's Encrypt -- a free, open and automated certificate authority (CA) provided as a service by the Internet Security -- can be used to get SSL certificates at no cost.

--------
In addition to SSL certificates linked to Domain Names, and issued for authenticating and encrypting data sent to and from Websites. CAs issue other types of Digital Certificate for different purposes including:

- Code Signing Certificates:

Code signing certificates are used by software publishers and developers to sign their software distributions.
End users can then use them to authenticate and validate software downloads from the vender or developer.

- Email Certificates: 

Email certificates enable entities to sign, encrypt, and authenticate email using the Secure Multipurpose Internet Mail Extension (S/MIME) protocol for secure email attachments.

- Device Certificates:

Device certificates can be issued to Internet of Things (IoT) devices to enable secure adminstration and authentication of software of firmware updates.
Iot, is a system of interrelated computing devices, mechanical, and digital machines, etc...

- Object Certificates:

Object certificates can be used to sign and authenticate any type of software object.

- User or Client Certificate:

User or Client Certificates are used by individuals for various authentication purposes, and are sometimes known as signature verification certificates.

CAs in recent years increasingly have shifted their business focus from issuing SSL certificates for Web Domains to providing a wider range of certification services.

--------
How a certificate authority works:

While there is no technical obstacle preventing an individual or organization from creating their own CA, publicly trusted CAs usually participate in the CA/Browser Forum, -- sometimes called the CA/B Forum -- which is the industry group governing how certificate authorities work with web browsers. Most members of the group are either CA or Web Browser vendors, but certificate consumer organizations also participate.

The CA/B Forum maintains guidelines for all aspects of the creation, distribution, and use of digital certificates in the web, including polices for certificate, and certificate revocation.

--------
CA activities start with a root certificate, which is used as the ultimate basis for trust in all certificates issued by the authority. The root certificate, along with the private key associated with that (root) certificate, is usually treated with the highest level of security, and is usually stored offline in a protected facility, and may be stored on a device that is unpowered except when the certificate is needed.

CA will use that root certificate to create intermediate certificates, which are the certificates used to sign the digital certificates issued by the authority. This allows the public to trust the issued certificates, while at the same time protecting the root in instances where an intermediate certificate expires or is revoked.

--------
Intermediate certificates may also be used for issuing digital certificates through registration authorities (RAs), entities to which a CA may delegate some or all of the requirements to authenticate the organization and domain identity for an entity seeking a certificate.

According to CA/B Forum rules, the CA must contractually require the RA to comply and document their compliance with CA/B Forum rules.

In addition, the CA is required to limit the RA to registering certificates within the domain namespace assigned to the RA.

--------
Failure to police its RAs was one of the behaviors cited against Symantec's Certificate Authority Operations, which ultimately led the company to divest responsibility for that business to DigiCert in 2017.

CAs themselves are also subject to extensive rules requiring operational audits, and infractions can bring down additional required audits and other consequences for any infractions or activies which might undermine trust in their operations. 

Prior to Symantec's divestiture of its CA operations, the CA/B Forum had called for a number of different consequences which Symantec failed to complete satisfactorily.
























































































