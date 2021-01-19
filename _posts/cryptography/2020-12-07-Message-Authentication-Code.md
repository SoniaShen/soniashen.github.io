This archive is based on: https://www.investopedia.com/terms/m/message-authentication-code.asp#:~:text=What%20Is%20a%20Message%20Authentication%20Code%3F%20A%20message,the%20message%20or%20request%20sent%20by%20the%20user.

Message Authwntication Code (MAC)
--------
What is a Message Authentication Code?

A message authentication code (MAC), or a tag, is a security code that is typed in by the user of a computer to access accounts ot portals. 

This code is attached to the message or request sent by the user. Message Authentication Code (MACs) attached to the message must be recognized by the receiving system in order to grant the user access.

--------
Understanding Message Authentication Code:

Message authentication codes (MACs) are commonly used in Electronic Funds Transfers (EFTs) to maintain information integrity. They confirm that a message os authentic; that is really dose come. In other words, from the stated sender, and hasn't undergo any changes en route. A verifier who also possesses the key can use it to identity changes to the content of the message in question (Symmetric Keys).

Message Authentication Codes are usually required to access any kind of financial account. Banks, brokerage firms, trust companies, and any other deposit, investment, or insurance company that offers online access can emply these codes. They are a vital compnoent of financial cryptography.

--------
Algorithms Used to Generate MACs (together):

Three algorithms typically comprise a MAC:
    A key generation algorithm;
    A signing algorithm;
    A verfying algorithm.

- The Key Generation Algorithm chooses a key at random;
- The Signing Algorithm sends a tag when gives the key and the message;
- The Verifying Algorithm is used to verify the authenticity of the message when give the key and tag.
    It will return a message of "accepted" if the message and tag are authentic and unaltered,
    but otherwise, it will returen a message of "rejected".

For example, the sender sends a message, such as an Electronic Fund Transfer (EFT), through the MAC algorithm, which generates a key and attaches a MAC data tag to the message. -> The recipient gets the message, runs it through the MAC algorithm with the same key, and gets a second data tag. He or she will then compare this MAC data tag with the first one attached to the message when it was transmitted. If the code is the same at both ends, the recipient can safely assume that the data Integrity of the message is intact. If not, however, it means that the message was altered, tamperes with or forged.

However, the message itself should contains some data that ensures that this messaga can only be sent once.
For example, a one-time Message Authentication Code (MAC), timestamp, or sequence number could be used guarantee that the message can only be sent once. Otherwise, the system could be vulnerable to a replay attack, in which an attacker intercepts the message after it has been decoded and retransmits it at a later time, replicating the original results and infiltrating the system. (DDoS)

--------
Message Integrity Codes (MICs):

Sometimes, the term Message Integrity Code (MICs) will be used instead of Message Authentication Code (MACs). This is most often done in the communications industry, where MAC traditionally means Media Access Control Address (MAC Address). However, MICs can also be uesd to refer to Message Digest (Hashes), which does not use secret keys in the same manner as a Message Authentication Code (MAC), and cannot offer the same level of the security without further encryption.




========
[web link: https://stackoverflow.com/questions/2836100/what-is-the-difference-between-a-hash-and-mac-message-authentication-code]

Different between a Hash and a MAC (Message Authentication Code):

The main different is conceptual:
    While Hashes are used to guarantee the Integrity of data;
    A MAC guarantees Integrity and Authentication.

This means that a Hashcode is bindly generated from the message without any kind of external input:
    what you obtain is something that can be used to check if the message got any alteration during its travel.

A Message Authentication Code (MACs) instead uses a private key as the seed to the hash function it uses when generating the code:
    this should assure the reveiver that, not only the message hasn't been modified, but also who sent it is what we were expecting. Otherwise, an attacker couldn't know the private key used to generate the code.

--------
According to wikipedia:

While MAC (Message Authentication Code) functions are similar to Cryptographic Hash Functions, they possess different security requirement.

To be considered secure, a MAC function must resist existential forgery under chosen-plaintext attacks. This means that even if an attacker has access to an Oracle which processes the secret key and generates MACs for messages of the attacker's choosing, the attacker cannot guess the MAC for other messages without performing infeasible amounts of computation.

--------
Of course, although their similarities, they are implemented in a different way:
    Usually, a MAC generation algorithm is based upon a Hash code generation algorithm with the extension that cares about using a private key.

========

------------------------+------+-----------+-------------
Cryptographic primitive | Hash |    MAC    | Digital
Security Goal           |      |           | signature
------------------------+------+-----------+-------------
Integrity               |  Yes |    Yes    |   Yes
Authentication          |  No  |    Yes    |   Yes
Non-repudiation         |  No  |    No     |   Yes
------------------------+------+-----------+-------------
Kind of keys            | none | symmetric | asymmetric
                        |      |    keys   |    keys
------------------------+------+-----------+-------------

Integrity -
    Can the recipient be confident that the message has not been accidentally modified?

Authentication -
    Can the recipient be confident that the message originates from the sender?

Non-repudiation -
    If the recipient passes the message and the proof to a third party, can the third party be confident that the message originated from the sender? (Only in the cryptography sense, not in the legal sense).

Note:
    Please remeber that authentication without confidence in the keys used is useless.
    For Digital Signature,
        a recipient must be confident that the verification key actually belong to the sender.
    For Message Authentication Code (MACs),
        a recipient must be confident that the shared symmetric key has only been shared with the sender.






































