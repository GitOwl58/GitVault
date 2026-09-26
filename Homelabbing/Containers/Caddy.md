#domain/homelab

# Caddy

A web server and **[[Reverse Proxy]]** that handles HTTPS automatically by default, point it at a domain and it obtains and renews the Let's Encrypt certificate itself, no separate step required. Configuration lives in a simple text file (a `Caddyfile`), often just a handful of lines per service, which makes it fast to set up once you're comfortable editing config rather than clicking through a UI like **[[Nginx Proxy Manager]]**.

```
sonarr.home.example.com {
    reverse_proxy sonarr:8989
}
```

A common middle ground between NPM's UI-driven simplicity and **[[Traefik]]**'s full container-label automation.

### Related
[[Infrastructure and Management]] [[Reverse Proxy]] [[Nginx Proxy Manager]] [[Traefik]]
