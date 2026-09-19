#domain/homelab

# Traefik

A **[[Reverse Proxy]]** built specifically to be container-aware: instead of manually configuring each proxied service (as with **[[Nginx Proxy Manager]]** or **[[Caddy]]**), Traefik watches the Docker API directly and picks up new services automatically from labels defined right in each container's **[[Docker Compose]]** file.

```yaml
labels:
  - "traefik.http.routers.sonarr.rule=Host(`sonarr.home.example.com`)"
```

The most automated of the three common reverse proxy choices, and the most common pick for larger, container-heavy homelabs where manually registering every new service would get tedious. The tradeoff is a steeper initial learning curve than NPM's UI or Caddy's simple config file.

### Related
[[Infrastructure and Management]] [[Reverse Proxy]] [[Docker Compose]] [[Nginx Proxy Manager]] [[Caddy]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
