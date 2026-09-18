#domain/networking

# ICMP (Internet Control Message Protocol)

Used by **ping** to determine the performance of a connection between devices: whether it exists and is reliable. ping sends an **Echo Request** (Type 8) and measures the round-trip time until the target's **Echo Reply** (Type 0) comes back. No reply can mean the target is down or a firewall is blocking it.

Syntax: `ping <IP address or website URL>`

**traceroute** (`tracert` on Windows) also relies on ICMP: it sends packets with increasing [[TTL]], and each router that drops a TTL-expired packet replies with an **ICMP Time Exceeded** (Type 11), revealing itself, hop by hop, until the target is reached.

### Related
[[IP address]] [[TTL]] [[Router]] [[Tcpdump]]
### Source:
[[15. What is Networking]]
[[13. Networking Essentials]]
[[17. Tcpdump The Basics]]
[[18. Nmap The Basics]]