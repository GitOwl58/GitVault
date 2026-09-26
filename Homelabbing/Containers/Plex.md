#domain/homelab

# Plex

A media server that organizes and streams your movie, TV, and music library, with polished client apps on essentially every platform (TVs, phones, consoles, browsers) and the easiest sharing experience of any option, invite a friend by email and they're watching within minutes.

### What changed in 2025-2026
Plex used to offer free remote streaming (watching your library from outside your home network) for its entire history. That changed on April 29, 2025, remote streaming now requires a paid Plex Pass or a cheaper "Remote Watch Pass". Pass pricing also rose sharply through 2026 (monthly and lifetime tiers both increased substantially). Local, in-home streaming remains free. This is the main reason a lot of the self-hosting community has been shifting toward **[[Jellyfin]]** for new setups, see **[[Media Servers]]**.

### Docker basics
```yaml
plex:
  image: plexinc/pms-docker
  network_mode: host
  volumes:
    - plex_config:/config
    - /nas/media:/media
  restart: unless-stopped
```
`network_mode: host` is the common setup, Plex's discovery/DLNA features rely on it working smoothly.

### Related
[[Media Servers]] [[Jellyfin]] [[Tautulli]] [[Self-Hosted Service Stack]]
