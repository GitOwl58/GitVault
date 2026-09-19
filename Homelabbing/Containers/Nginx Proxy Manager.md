#domain/homelab

# Nginx Proxy Manager

The most beginner-friendly **[[Reverse Proxy]]** option, a web UI over Nginx that lets you add a "proxy host" (a domain pointing at an internal service and port) and request/renew a Let's Encrypt TLS certificate for it, all through forms rather than editing config files by hand.

Good default choice for a first reverse proxy setup, the tradeoff versus **[[Caddy]]** or **[[Traefik]]** is that it's less automated, each new service means manually adding a proxy host through the UI rather than having it discovered automatically from container labels.

### Related
[[Infrastructure and Management]] [[Reverse Proxy]] [[Caddy]] [[Traefik]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
