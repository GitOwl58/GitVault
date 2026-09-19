#domain/homelab

# VPNs and Remote Access

How to reach the homelab from outside the home network without exposing every service directly to the internet. All of the options below build on the same underlying idea, an encrypted tunnel back into the home network, but differ a lot in setup effort.

### Options
- **[[WireGuard]]** run directly: fastest and fully self-hosted, but manual key management and usually a forwarded UDP port on the router.
- **[[Tailscale]]**: WireGuard under the hood, with automatic key exchange and NAT traversal, so most connections work without touching the router at all. Free for personal use up to 6 users with unlimited devices per user, the easiest on-ramp for a first remote-access setup.
- **[[Netbird]]**: a fully open-source alternative to Tailscale, same WireGuard-based mesh idea, but with a self-hostable control plane (via Headscale-style setups or Netbird's own), appealing if avoiding a third-party coordination server entirely matters to you.
- **OpenVPN**: the older standard, still works fine, but slower and more complex to configure than WireGuard-based options, mostly relevant now for compatibility with older hardware/firmware that doesn't support WireGuard.

### Which to pick
For a first homelab, Tailscale gets remote access working in minutes and is genuinely free at homelab scale. Reach for plain WireGuard or Netbird specifically when keeping every component self-hosted, including the coordination/key-exchange layer, matters more than setup speed.

### Related
[[WireGuard]] [[Tailscale]] [[Netbird]] [[Homelab Networking Basics]] [[Self-Hosted Service Stack]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
