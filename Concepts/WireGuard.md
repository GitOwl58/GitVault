#domain/homelab

# WireGuard

A modern VPN protocol, built into the Linux kernel, designed to be simpler, faster, and easier to audit than older VPN protocols like OpenVPN or IPsec. It uses a small, fixed set of modern cryptographic primitives rather than the older protocols' large menu of negotiable (and sometimes weaker) options, which is a big part of why it's easier to reason about securely.

### How it's used in a homelab
WireGuard creates an encrypted tunnel between two points, most commonly a phone/laptop out in the world and the homelab's router or a dedicated WireGuard host, so remote devices can reach internal services as though they were on the home network. Setup is key-pair based: each peer has a public/private key pair, and a small config file defines which peers can talk to which.

Running it directly usually means generating keys manually and forwarding a UDP port on the router, straightforward but with a bit of setup friction. **Tailscale** (and similar tools like Netbird, Headscale for a self-hosted control plane) builds on top of WireGuard, automating key exchange and NAT traversal so two devices can connect without manual port forwarding in most cases, a popular easier on-ramp for a first remote-access setup, see **[[Homelab Networking Basics]]**.

### Related
[[Homelab Networking Basics]] [[Self-Hosted Service Stack]] [[Firewall]] [[Reverse Proxy]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
