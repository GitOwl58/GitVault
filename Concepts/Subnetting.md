#domain/networking

# Subnetting

Splitting a network into smaller networks by masking part of the [[IP address]]. A subnet mask is 4 bytes / 32 bits like an IP address (e.g. `255.255.255.0`, or written as CIDR `/24` — the leftmost 24 bits are fixed across the subnet).

Within a subnet:
- **Network address** — first address, identifies the subnet itself (e.g. `192.168.1.0`)
- **Broadcast address** — last address, targets every host on the subnet (e.g. `192.168.1.255`)
- **Host address** — everything in between, assignable to a device
- **Default gateway** — usually one of these, sends traffic destined outside the subnet

Private IP ranges (RFC 1918) — not routable on the public Internet, need [[NAT]] via a router with a public IP to get out:
- `10.0.0.0 – 10.255.255.255` (10/8)
- `172.16.0.0 – 172.31.255.255` (172.16/12)
- `192.168.0.0 – 192.168.255.255` (192.168/16)

### Related
[[IP address]]
[[NAT]]
[[Routing]]
[[Networking]]

### Source:
[[16. Intro to LAN]]
[[12. Networking Concepts]]
