# DoH (DNS over HTTPS)

#domain/networking #domain/security #type/concept 

DNS resolution tunneled inside HTTPS, over the same **port 443** used for normal web traffic.

## What it protects
Same core benefits as [[DoT]] — confidentiality of queries, resolver authenticity via TLS.

## Key difference from DoT
- **Blends in** — indistinguishable from regular HTTPS traffic on the wire, so it's much harder to block or censor
- Often implemented **per-application** (browsers doing their own DoH) rather than at the OS/system level — fragments DNS handling across apps instead of one unified system resolver

## Trade-offs vs DoT
- Harder to monitor/firewall specifically as DNS traffic (feature for censorship resistance, downside for lab visibility/network monitoring)
- Best fit: hostile/restrictive networks that block DNS-looking traffic (hotels, some corporate/national networks)
- DoT better fit: full system control, clear separation of DNS traffic for monitoring/analysis (labs, learning, enterprise visibility)

## Related
- [[DNS over TLS (DoT)]]
- [[DNSSEC]]
### Source:
[[DNS over TLS]]