#domain/homelab

# Tailscale

A mesh VPN built on **[[WireGuard]]**, but with the setup friction removed: instead of manually generating and distributing key pairs, each device authenticates once (via an account) and Tailscale's coordination servers handle key exchange and NAT traversal automatically, so devices connect directly to each other in most cases without any port forwarding on the router.

Can also be run as a container inside the homelab itself (rather than just as a client app on personal devices), letting the whole homelab's Docker network join the Tailscale mesh, or exposing specific services to it, without every individual container needing its own Tailscale setup.

### Free tier, as of 2026
Tailscale's Personal plan counts *people*, not devices, up to 6 users, each with unlimited devices of their own, plus 50 "tagged" resources (servers/routers registered with a tag rather than tied to a person) and 1,000 ephemeral-node minutes a month. Genuinely enough for a typical homelab plus household without paying anything.

### The tradeoff
Key exchange and coordination go through Tailscale's own servers (the actual traffic, once connected, is still a direct encrypted WireGuard tunnel between your devices, not routed through Tailscale). For a fully self-hosted alternative to even that coordination layer, see **[[Netbird]]**.

### Related
[[VPNs and Remote Access]] [[WireGuard]] [[Netbird]] [[Homelab Networking Basics]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
