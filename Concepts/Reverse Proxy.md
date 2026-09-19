#domain/homelab

# Reverse Proxy

A service that sits in front of other internal services and routes incoming requests to the right one, based on the domain name or path requested, while presenting a single entry point to the outside world. Instead of remembering `192.168.1.50:8989` for Sonarr and `192.168.1.50:7878` for Radarr, a reverse proxy lets each service live at its own subdomain (`sonarr.home.example.com`, `radarr.home.example.com`) on the standard web ports.

Beyond routing, a reverse proxy typically also handles **TLS termination**, obtaining and renewing HTTPS certificates (often automatically via Let's Encrypt) so traffic is encrypted without every individual service needing its own certificate setup.

### Common options
- **Nginx Proxy Manager**: the most beginner-friendly, web UI for managing proxy hosts and certificates.
- **SWAG** (Secure Web Application Gateway): Nginx plus automated Let's Encrypt, favored in the linuxserver.io ecosystem.
- **Caddy**: config-file-based, automatic HTTPS by default, popular for its simplicity once you're comfortable with text config over a UI.
- **Traefik**: dynamic, container-aware (auto-discovers Docker services via labels), common in larger or more automated setups.

### Security note
A reverse proxy is the front door if any homelab service is exposed to the internet, which is exactly why it's usually paired with network segmentation (its own **VLAN**) so a compromised exposed service can't freely reach the rest of the homelab.

### Related
[[Self-Hosted Service Stack]] [[Homelab Networking Basics]] [[Homelab Common Mistakes]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
