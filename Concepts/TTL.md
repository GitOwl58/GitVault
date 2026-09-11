#type/concept #domain/networking

# TTL (Time to Live)

A header field that sets an expiry timer on a [[Packet]], so it doesn't clog the network if it never reaches its destination.

Also applies to [[DNS record]]s — determines how long a resolver caches a response before it must be looked up again.

Each router along a path decrements a packet's TTL by one; a router that decrements it to zero drops the packet and replies with an **ICMP Time Exceeded** — the mechanism **traceroute** uses to reveal each hop.
### Related
[[DNS Record]] [[Packet]] [[CDN]] [[Header]] [[Networking]] [[ICMP]]
### Source:
[[18. Packets and Frames]]
[[20. DNS in details]]
[[13. Networking Essentials]]

