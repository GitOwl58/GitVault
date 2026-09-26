#domain/homelab

# Infrastructure and Management

The "meta" containers, they don't do anything user-facing themselves, they manage and expose everything else.

### Options
- **[[Portainer]]**: a web UI for managing Docker (and Docker Swarm/Kubernetes) without living in the CLI, browse containers, view logs, redeploy stacks, all from a browser.
- **[[Watchtower]]**: watches running containers and automatically pulls and applies newer images, on a schedule you set, useful but worth pairing with backups since an automatic update can occasionally break something.
- **[[Nginx Proxy Manager]]**, **[[Caddy]]**, **[[Traefik]]**: the three most common **[[Reverse Proxy]]** choices, routing a domain to the right internal service and handling TLS. NPM is the easiest via its web UI, Caddy is the simplest config-file approach, Traefik is the most automated for larger, container-heavy setups.

### Related
[[Reverse Proxy]] [[Self-Hosted Service Stack]] [[Docker]] [[Docker Compose]]
