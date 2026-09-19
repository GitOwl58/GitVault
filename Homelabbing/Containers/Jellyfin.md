#domain/homelab

# Jellyfin

A fully open-source, free media server, a community-driven fork of the old Emby codebase from before Emby went closed-source/freemium. Organizes and streams movies, TV, and music, the same core job as **[[Plex]]**, but with no paid tier for any feature, including remote streaming and hardware-accelerated transcoding, both of which Plex now gates behind a subscription.

### Tradeoffs versus Plex
Client apps are solid but generally a step behind Plex's polish, and there's no built-in zero-config remote access or dead-simple friend-sharing flow, you pair it with a **[[Reverse Proxy]]** or a VPN (see **[[VPNs and Remote Access]]**) for access from outside the home. In exchange: no account requirement, no external dependency on a company's servers, and no risk of a future pricing change.

### Docker basics
```yaml
jellyfin:
  image: jellyfin/jellyfin
  ports:
    - "8096:8096"
  volumes:
    - jellyfin_config:/config
    - /nas/media:/media
  restart: unless-stopped
```

### Related
[[Media Servers]] [[Plex]] [[Seerr]] [[Reverse Proxy]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
