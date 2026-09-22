#domain/homelab

# Self-Hosted Service Stack

What actually runs on a homelab, once the hardware and networking are sorted. **[[Docker]]** (and **Docker Compose** to define multi-container stacks in one file) is the near-universal packaging format, with the "one service per container" philosophy: each service gets its own isolated container so it can be updated, restarted, or snapshotted independently without touching the others. On **[[Proxmox]]**, the same idea extends one level up: many homelabbers run one **LXC container per major service group** as well, for even stronger isolation, fault containment, and independent snapshotting, with a new service typically spinning up in well under a minute once the pattern is set.

### The container catalog, by category
The full catalog, one atomic note per container app, now lives in its own `Containers/` subfolder, organized into category hub notes. Quick map:

- **[[Media Servers]]**: Plex, Jellyfin, and the tradeoffs between them.
- **[[Media Management (Arr Stack)]]**: Sonarr, Radarr, Prowlarr, Bazarr, Readarr, Tdarr, Seerr, Tautulli, Audiobookshelf, qBittorrent, SABnzbd, the automation pipeline that acquires and organizes media.
- **[[Password Managers]]**: Vaultwarden and why it's the default over Bitwarden's own official server.
- **[[VPNs and Remote Access]]**: WireGuard, Tailscale, Netbird, and OpenVPN, how to reach the homelab from outside.
- **[[Infrastructure and Management]]**: Portainer, Watchtower, and the three common reverse proxies (Nginx Proxy Manager, Caddy, Traefik).
- **[[Monitoring]]**: Uptime Kuma for simple checks, Prometheus/Grafana for deeper metrics.
- **[[Network-wide Ad Blocking]]**: Pi-hole and AdGuard Home.
- **[[Smart Home]]**: Home Assistant, Mosquitto/MQTT, and a couple of niche extras.
- **[[Photos and Files]]**: Immich and Nextcloud, self-hosted alternatives to Google Photos/Dropbox.
- **[[Miscellaneous]]**: Grocy, a self-hosted Minecraft server.

Worth knowing before picking a media server: Plex restructured its pricing through 2025-2026, remote streaming (accessing your library from outside your home network) now requires a paid Plex Pass or a cheaper remote-only plan, something that used to be free. That shift has pushed a lot of the self-hosting community toward **Jellyfin**, which stays fully free including remote streaming and hardware transcoding, at the cost of a slightly less polished app ecosystem and no built-in zero-config remote access (pair it with a **[[Reverse Proxy]]** (not beginner recommended)or **[[Tailscale]]** for that). Plex still wins for non-technical households who just want it to work everywhere with zero setup. See **[[Media Servers]]** for the full comparison.

---
### Example docker-compose.yml snippets

Core infrastructure stack (Portainer, Watchtower, Nginx Proxy Manager):
```yaml
services:
  portainer:
    image: portainer/portainer-ce:latest
    ports:
      - "9000:9000"
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - portainer_data:/data
    restart: unless-stopped

  watchtower:
    image: containrrr/watchtower
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    command: --schedule "0 0 4 * * *"
    restart: unless-stopped

  nginx-proxy-manager:
    image: jc21/nginx-proxy-manager:latest
    ports:
      - "80:80"
      - "443:443"
      - "81:81"
    volumes:
      - npm_data:/data
      - npm_letsencrypt:/etc/letsencrypt
    restart: unless-stopped

volumes:
  portainer_data:
  npm_data:
  npm_letsencrypt:
```

Media stack (Plex, Sonarr, Radarr):
```yaml
services:
  plex:
    image: plexinc/pms-docker
    network_mode: host
    volumes:
      - plex_config:/config
      - /nas/media:/media
    restart: unless-stopped

  sonarr:
    image: linuxserver/sonarr
    ports:
      - "8989:8989"
    volumes:
      - sonarr_config:/config
      - /nas/media/tv:/tv
    restart: unless-stopped

  radarr:
    image: linuxserver/radarr
    ports:
      - "7878:7878"
    volumes:
      - radarr_config:/config
      - /nas/media/movies:/movies
    restart: unless-stopped

volumes:
  plex_config:
  sonarr_config:
  radarr_config:
```

Monitoring stack (Prometheus, Grafana, Node Exporter):
```yaml
services:
  prometheus:
    image: prom/prometheus
    ports:
      - "9090:9090"
    volumes:
      - ./prometheus.yml:/etc/prometheus/prometheus.yml
    restart: unless-stopped

  grafana:
    image: grafana/grafana
    ports:
      - "3000:3000"
    volumes:
      - grafana_data:/var/lib/grafana
    restart: unless-stopped

  node-exporter:
    image: prom/node-exporter
    ports:
      - "9100:9100"
    restart: unless-stopped

volumes:
  grafana_data:
```

---
### Mounting NAS storage over NFS
Most of these services need access to shared storage (media libraries, download folders) rather than storing large files inside the container host itself. A typical **[[NFS]]** mount to a **[[NAS]]**:
```bash
apt install nfs-common
mkdir /nas
```
Add to `/etc/fstab` for a persistent mount across reboots:
```
192.168.1.50:/volume1/media  /nas  nfs  defaults  0  0
```
Then:
```bash
systemctl daemon-reload
mount /nas
```

### The shape of it, end to end
Clients (phones, laptops, browsers) → reverse proxy (handles the domain name and TLS) → the Proxmox host's LXC containers, each running one service → NFS mount → the NAS, holding the actual data. The reverse proxy is the single door in from outside; everything behind it stays on the private network.

### Related
[[Homelab Setup]] [[Docker]] [[Docker Compose]] [[Proxmox]] [[Container]] [[Homelab Networking Basics]] [[Reverse Proxy]] [[NFS]] [[NAS]] [[Media Servers]] [[Media Management (Arr Stack)]] [[Password Managers]] [[VPNs and Remote Access]] [[Infrastructure and Management]] [[Monitoring]] [[Network-wide Ad Blocking]] [[Smart Home]] [[Photos and Files]] [[Miscellaneous]]

### Source:
Synthesized from external homelab guides and my homelab setup.
