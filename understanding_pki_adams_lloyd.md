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
- Two researchers - Diffie and Hellman - introduced the idea of ciphers which were asymmetric in which the key for encryption and the key for decryption are related but conspicuously different.
- The keys in the key pair (public and private key) are different, but they are also related.
  - One (public) is used for encryption of plaintext whereas the other (private) is used decryption of ciphertext.
- The relationship between the keys in the key pair is mathematical in nature and may rely on information known only to the creator of the key pair.
  - Security in this technology is such that it is computationally infeasible for anyone other than the key pair creator to derive the private key from knowledge of the public key.
    - Theoretically, this doesn't mean that derivation of the private key is impossible. However, the amount of time, memory, or computing power necessary to do so in practice must be prohibitively high.
- Many of the drawbacks of SC can now be addressed:
  - Security between strangers - the public key can be shared widely amongst strangers given the difficulty of computing the private key even if all other details of the cipher are known. Thus, even if two parties are unknown to each other, one can look up the public key of the other and protect data from the other.
    - The caveat here is that the retrieving party must be confident that the public key belongs to the other one. There are two methods to achieving this confidence:
      - The retrieving party trusts the repository from which the public key has been retrieved.
      - The retrieving party finds a way to trust the repository, usually via a public-key certificate. This means that the information provided by the repository must be independently verifiable.
  - Digital signature - analogous to a handwritten signature because a single entity can sign some data, but any number of entities can read the signature and verify its accuracy.
    - There must be a private key known only to Alice so that when she signs some data, the data is uniquely and explicitly tied to her. Furthermore, a public key must be available to a wider group of entities (potentially all entities) so that the signature can be verified and identified with Alice.
    - Since it is computationally infeasible to forge a private key, it is impossible to forge the digital signature as well.
    - A digital signature provides both data origin authentication (evidence about who originated the data) and data integrity (evidence that the data has not been altered in any way)
  - Key establishment - Public-key cryptography can also be used to perform key exchange between two entities:
    - Key transfer - One entity can encrypt a symmetric key using another entity's public key
    - Key agreement - Both entities jointly-contribute to the genereation of the symmetric key
- Encryption of data in ASC
  - Computations used for data encryption via ASC are too slow and thus impractical for many environments. Instead, the preferred route is a two-step process:
    - The data is encrypted using a randomly-generated symmetric key
    - The symmetric key is then encrypted using the public key
  - The steps required to decrypt are two-fold as well: one to decrypt the symmetric key using the private key and the other to decrypt the ciphertext using the decrypted symmetric key.
- Public key algorithms
  - 



