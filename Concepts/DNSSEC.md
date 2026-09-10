# DNSSEC

#domain/networking #domain/security #type/concept 

Cryptographic signing of DNS records, validated through a chain of trust from the root zone down to the domain (root → TLD → domain).

## What it protects
- **Data authenticity/integrity** — proves the DNS response hasn't been forged or tampered with, regardless of transport
- Defends against [[DNS spoofing]] / cache poisoning — a forged response won't have a valid signature and gets rejected

## What it does NOT protect
- Doesn't encrypt anything — a DNSSEC response can still be read in plaintext by anyone on-path. That's [[DoT]]/[[DoH]]'s job, not DNSSEC's
- Strict mode (`DNSSEC=yes`) can break resolution entirely for domains with broken/misconfigured signing chains — real and common enough to expect

## Complementary to DoT/DoH, not redundant
- [[DoT]]/[[DoH]] protect the **path** (query can't be read or altered in transit)
- DNSSEC protects the **data** (response is provably authentic all the way back to the source, even if the resolver itself lied or was compromised)
- Using DoT without DNSSEC = you trust your resolver blindly. Using both = trust is externally verifiable.

## Related
- [[DNS over TLS (DoT)|DoT]]
- [[DoH]]
- [[DNS spoofing]] / [[MITM]]
### Source:
[[DNS over TLS]]
