#domain/security

### Certificate (HTTPS context)
An HTTPS digital certificate binds a server's public key to its domain name, wrapped in a cryptographic signature from a trusted Certificate Authority (CA) proving the ownership of that public key, to prevent tampering and impersonation.

Getting one signed starts with a Certificate Signing Request (CSR) submitted to a CA; the CA verifies it and issues the signed certificate (paid annually, or free via Let's Encrypt). A client trusts it by having that CA's own certificate in its local trusted-CA store. A **self-signed certificate** skips the CA entirely: no third party vouches for it, so it can't prove server authenticity.

### Related
[[Cryptography]]  [[HTTP|HTTPS]] [[CIA Triad]]

### Source
[[19. Extending your network]]
[[25. Cryptography concepts]]
[[15. Networking Secure Protocols]]