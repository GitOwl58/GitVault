#domain/security #domain/pentesting
# DNS Spoofing 



Attack where a forged DNS response is injected before the legitimate one arrives, tricking the victim into resolving a domain to an attacker-controlled IP.

## Mechanism
- Attacker positioned on-path (e.g. via [[ARP spoofing]] on a LAN) sniffs outgoing DNS queries
- Races the real DNS server, replying first with a forged response
- Victim's resolver accepts whichever response arrives first (no source validation in plaintext DNS)

## Why plaintext DNS is vulnerable
- No encryption → attacker can read the query to know what to forge
- No authentication → nothing stops a forged response from being accepted as legitimate

## Defenses
- [[DNSSEC]] — forged response won't carry a valid signature, gets rejected regardless of network position
- DoT / [[DoH]] — query is encrypted, harder for on-path attacker to see/target; cert pinning prevents impersonating the resolver itself
- Network segmentation — limits attacker's ability to get on-path in the first place

## Lab tool
`dnsspoof` (part of `dsniff`) — practical tool for testing this attack in Attacker-Defender lab

## Related
- [[DNS over TLS (DoT)|DoT]]
- [[DNSSEC]]
