---
aliases: [SSL, TLS/SSL]
---
#domain/networking #domain/security

# TLS (Transport Layer Security)

Cryptographic protocol at the OSI transport layer that secures an existing protocol's communication: the appended "S" (HTTPS, SMTPS, [[DNS over TLS (DoT)|DoT]], MQTTS...) marks TLS underneath. Descended from Netscape's SSL (SSL 2.0, 1995); the IETF's TLS 1.0 (1999) was an upgrade to SSL 3.0, and TLS 1.3 (2018) is the current, heavily revised version. Protects [[Confidentiality]] (no one can read the data), [[Integrity]] (no one can alter it), and authenticity (the server is really who it claims to be), the last backed by a [[Certificate]] chain to a trusted Certificate Authority.

### Related
[[Certificate]] [[Encryption]] [[Cryptography]] [[HTTP|HTTPS]] [[SSH]] [[VPN]] [[DNS over TLS (DoT)|DoT]]

### Source:
[[15. Networking Secure Protocols]]
