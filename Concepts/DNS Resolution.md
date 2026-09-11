#domain/networking

# DNS Resolution

The lookup chain when resolving a domain:
1. Local cache (your device)
2. Recursive DNS server (ISP or custom) — has its own cache
3. Root DNS server — redirects based on [[TLD]]
4. TLD server — points to the authoritative server
5. Authoritative server — returns the actual record, cached per its [[TTL]]

### Related:
[[DNS]] · [[TTL]]

### Source:
[[20. DNS in details]]