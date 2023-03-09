## Motivations for PKI
- PKI can be used as the underlying technology to support authentication, integrity, confidentiality, and non-repudiation.
  - Non-repudiation - Assurance that the sender of information is provided with proof of delivery and the recipient is provided with proof of the sender's identify, so neither can later deny having processed the information.
- How can PKI give a positive return on investment? Judicious deployment of a single, unifying PKI technology can help, among other things:
  - Reduce administrative overhead
  - Reduce the number of passwords required by end users
  - Reduce paperwork and improve workflow efficiencies through more automation
  - Optimize work-force productivity by minimizing the amount of time required to spend on security infrastructure

## Part I: Concepts
### Public-Key Cryptogrpahy
- Two categories of mechanisms exist for performing the transformation of text to gibberish and back: symmetric (secret key) vs. asymmetric ciphers (public key)
  
#### Secret key aka symmetric cryptography (SC)
- The sender and the intended recipient share some secret information specifying how the transformation is to be performed.
- The shared secret information specifying exactly how the transformation to and from gibberish is to be accomplished - e.g., the number of places in a simple substitution cipher - is called a key.
- The transformation to gibberish is called encryption. Plaintext in, ciphertext out.
- The transformation to plaintext is called decryption. Ciphertext in, plaintext out.
- The entire confidentiality mechanism (aka the encryption and decryption algorithms) is called a cipher.
  - In this setting, the cipher is a symmetric cipher especially if one of the following is true:
    - Encryption key and decryption key are identical.
    - One key is easily derived from the other.
- Desirable characteristics of symmetric encryption include:
  - small implementation footprint
  - encryption/decryption sizes
- Drawbacks include:
  - The need for secret key exchange
    - Secret key encryption requires that only the sender and recipient have access to the cipher. This requires a separate, out-of-band communication channel to share the cipher securely. This additional need may not always be met for everyone.
  - Difficulty initiating secure communication between previously unknown parties
    - The need for a secure, out-of-band channel to share the cipher becomes even more difficult when the parties involved are unknown to each other.
    - The concept of an "introducer" is needed to introduce the sender and the recipient. This concept is not unique to SC or asymmetric cryptography (ASC) or even real-life for that matter. The government that issues a driver's license is an introducer.
  - Difficulties of scale
    - If each pair of actors require a unique secret key then provisioning and maintaining secret keyrs for large communities becomes intractable quickly. Manageability also becomes an issue because keys do not last forever and need replacing periodically.
- Symmetric Central Server Architectures (CSA) are a way to mitigate some of the problems listed above. In this setup:
- The community shares a secret key with the central server often called a Key Distribution Center (KDC)
- The number of secret keys that need to be stored and maintained in a community is essentially equal to the number of users in the community
- The KDC can also act as an introducer to actors that are previously unknown to each other
- Drawback with this approach is that the KDC becomes a single point of failure, must have 100% uptime, and may become a bottleneck for communication

#### Public key aka asymmetric cryptography (ASC)


