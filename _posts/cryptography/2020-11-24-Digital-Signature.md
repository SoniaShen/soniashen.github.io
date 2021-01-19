This archive is based on https://searchsecurity.techtarget.com/definition/digital-signature

--------
A digital signature is a mathematical technique used to validate the authenticity and integrity of a message, a software, or a digital document.  As the digital equvilent of a handwritten signature or a stamped seal, a digital offers far more inherent security, and it is intended to solve the problem of tampering and impersonation in digital communications.

Digital signatures can provide the added assurances of evidence of origin, identity and status of an electronic document, tanscation, or message and can acknowledge informed consent of the signer.

In many contries, including the USA, digital signatures are considered legally binding in the same way as traditional document signatures.

--------
Digital signatures work through public key crypotogtaphy's two mutually-authenticating crypotographic keys. The individuals who is creating the digital siginature uses their own private key to encrypt signature-related data (hash the message); the only way to decrypt that data is with the signer's public key. This is how digital sigatures are authentucated.

Digital signature technology requires all the parties to trust that the individual creating the sigature has been able to keep their own private key secret. If someone else has access to the signer's private key, that party could create fraudulent digital signatures in the name of the private key holder.

--------
To create a digital signature, signing software (i.e. email programe) creates a one-way hash of the electronic data to be signed. The private key is then used to encrypt the hash. The encrypted hash along with other information, such as the hashing algorithm IS the digital signature.

The reason for encrypting the hash instead of the entire messaga or document is that a hash function can convert an arbitary input into a fixed length value, which is usually much shotter. This saves time as hashing is much faster than signing.

The value of hash is unique to the hashed data. Any change in the data, even a change in a single character, will result in a different value. This attribute enables others to validate the integrity of the data by using the signer's public key to decrypt the encrypted hash value.

If the decrypted hash mactches a second computed hash of the same data, it proves that the data hasn't changed since it was signed. If the two hashes don't match, the data has either been tampered with in some way (i.e. a compromise to its integrity); or the signature was created with a private key that doesn't correspond to the public key presented by the signer, which shows an issue with authentication.

A digital signature can be used with any kind of message, whether the message is encrypted or not, simply so the receiver can be sure of the sender's identity and that the message arrived intact. Digital signatures make it difficult for the signer to deny having signed something (assuming their private key has not been compromised), as the digital signature is unique to both the document and the signer, and it binds them together. This property is called non-repudiation.

Digital signatures are not to be confused with digital certificates.

--------
[Digital Certificate, see web link: https://searchsecurity.techtarget.com/definition/digital-certificate]
Digital Certificate - AKA public key certificate.
    Which is used to cryptographically link ownership of a public key with the entity that owns this public key.
    A digital certificate, is an electronic document that contains
        the digital signature of the issuing certificate authority (i.e. CA);
        binds together a public key with an identity/entity/owner;
    It can be used to verify that a publickey belongs to a particular person or entity.

--------
Most modern email programs support the use of digital signature and digital certufucates, making it easy to sign any outgoing emails and validate digitally signed incoming messages. Digital signatures are also used extensively to provide proof of authenticity, data integrity, and non-repudiation of communications and transctions conducted over the internet.

There are three classes of digital signatures.
Class 1:
    Cannot be uesd for legal business documents as they are validated based only on an email ID and username.
    Class 1 digital signatures provide a basic level of security and are used in environments with a low risk of data compromise.

Class 2:
    Often used for e-filling of tax documents, including income tax returns, and Goods and Service Tax (GST) returns.
    Class 2 Digital Signatures authenticate a signee's identity against a pre-verified database.
    Class 2 Digital Signatures are used in environments where the risks and consequences of data compromise are moderate.

 Class 3:
    The higiest level of digital signatures.
    Class 3 digital signatures require a person or organization to present in front of a certifying authority to provide their identity before signing.
    Class 3 digital signatures are used for e-auctions, e-tendering, e-ticketing, court fillings.
    Class 3 digital signatures are used in other environments where threats to data or the consequences of a security failure are high.

--------
Uses of Digital Signatures:

Industries use digital signature technology to streamline processes and improve document integrity. Industries that use digital signatures include:

Government - 
    Digital Sigatures are used by governments worldwide for a variety of uses, including processing tax returns, verifying business-to-government (B2G) transactions, ratifying laws, and managing contracts. Most government entities must adhere to strict laws, regulations and standards when using digital sigatures.

Healthcare -
    Digital Signatures are used in the healthcare to improve the efficiency of treatment and administrative processes, to strengthen data security, for e-prescribing and hospitak admissions.

Manufacturing - 
    Manufacturing companies use digital signatures to speed up processes, including product design, quality assurance (QA), manufacturing enhancements, marketing and sales. The use of digital signatures in manufacturing is governed by the International Organization for Standard (ISO) and etcetera...

Financial Sercices -
    The U.S. financial sector uses digital signatures for contracts, paperiess banking, loan processing, insurance documentation, mortgages, etcetera...

--------
Digital Signature v.s. Electronic Signature

Though the two terms sound similar, digital signatures are different from electronic signatures. While digital signature is a technical term, defining the result of a ctyptographic process that can be used to authenticate a sequence of data, the term electronic signature or e-signature is a legal term that is defined legislatively.

For example, in the United States, the term was defined in the Electronic Signatures in Global and National Commerce Act, passed in 2000, as meaning "an electronic sound, symbol, or process, attached to or logically associated with a contract or other record and executed or adopted by a person with the intent to sign the record."

This means that a digital signature, which can be expressed digitally in electronic form and associated with the representation of a record, can be a type of electronic signature. More generally though, an electronic signature can be as simple as the signer's name being entered on a form on a webpage.

To be considered valid, electronic signature schemes must include three things:
    - a way to verify the identity of the entity signing it;
    - a way to verify that the signing entity intended to affirm the document being signed;
    - a way to verify that the electronic signature is indeed associated with the signed document.

A digital signature (compare to electronic signature) can, on its own, fulfill these requirements to serve as an electronic signature:
    - the public key of the digital signature is linked to the signing entity's identification;
    - the digital signature can only be affixed by the holder of the public key's associated private key, which implies the entity intends to use it for the signature;
    - the digital signature will only authenticate if the signed data, document, or representation of a document is unchanged. If a document is altered after being signed, the digital signature will fail to authenticate.

While authenticated digital signatures provide crypotographic proof that a document was signed by the stated entity and that the document has not been altered, not all electronic signatures can provide the same guatantees.

--------
Digital signature security features and benefits:

Security features embedded in digital signatures ensure that a document is not altered and that signatures are legitimate. Security features and methods uesd in digital signatures included:

PIN, password and code - 
    Used to authenticate and verify a signee's identity and approve theiy signature. Email, username and password is most common.

Time stamping -
    Provides the data and time of a signature. Time stamping is useful when the timing of a digital signature is critical, such as stock trades, lottery ticket issuance and legal proceedings.

Asymmetric cryptography -
    Employs a public key algorithm that includes private and public key encryption/authentication.

Checksum - 
    A long string of letters and numbers that represent the sum of the correct digist in a piece of digital data, against which comparisons can be made to detect errors or changes. Checksum acts as a data fingerprint.

    [Checksum algorithm, i.e. MD5, SHA-256, etcetra...
    See web link: https://searchsecurity.techtarget.com/definition/checksum]

Cyclic Redundancy Checking (CRC) -
    An error-detecting code and verification feature used in digital networks and storage devices to detect changes to raw data.

    [Cyclic Redundancy Checking is a method of checking for errors in data that has been transmitted on a communications link.
    See web link: https://searchnetworking.techtarget.com/definition/cyclic-redundancy-checking]

Certificate Authority (CA)  validation -
    CAs issue digital signatures and act as a trusted third party by accepting, authenticating, issuing, and maintaining digital certificates. The use of CAs helps avoid the creation of fake digital signatures.

    [CA - see web link: https://searchsecurity.techtarget.com/definition/certificate-authority]

Trust Service Provider (TSP) validation -
    A TSP is a person or legal entity that performs validation of s digital signature on a company's behalf and offers signature validation reports.

    







































































































