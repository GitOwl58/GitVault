---
aliases:
  - DoT
---
#domain/networking  #domain/security  #type/concept 
# DNS over TLS (DoT)



DNS resolution encrypted inside a TLS session, sent over **port 853** (instead of plaintext UDP/53).

## What it protects
- **Confidentiality** — on-path observers can't see which domains you're resolving
- **Server authenticity** — cert pinning (`IP#hostname`) verifies you're actually talking to the resolver you configured, not an MITM

## What it does NOT protect
- Doesn't hide *that* you're doing DNS (port 853 is identifiable/blockable — unlike [[DoH]])
- Doesn't validate the DNS *data* itself — that's [[DNSSEC]]'s job, not DoT's
- Resolver (e.g. Cloudflare) still sees all your queries in plaintext on their end — trust is shifted, not removed
- No protection if the endpoint itself is compromised

## vs DoH
Same goal, different port/blending strategy. DoT = distinct port (853), easy to monitor/firewall as DNS. [[DoH]] = tunneled over 443, blends with HTTPS, harder to block/censor but harder to distinguish from normal web traffic too.

## Related
- [[DNSSEC]] — authenticity of the DNS *data*, not the transport
- [[DoH]]
- [[DNS spoofing]] / [[MITM]] — the attack DoT's cert pinning defends against
# DOT



### Related

### Source:
[[DNS over TLS]]