#domain/homelab

# Seerr

A request-management front end: a friendly UI (and often the only part of the Arr stack that non-technical household members ever see) where someone can search for a movie or show and click "request," which then flows into **[[Radarr]]**/**[[Sonarr]]** automatically.

### What to know in 2026
This used to be two separate, competing projects, **Overseerr** (Plex-focused) and **Jellyseerr** (a Jellyfin/Emby-focused fork of Overseerr). On February 10, 2026 the two development teams officially merged into a single unified project called **Seerr**, combining Overseerr's polish with Jellyseerr's multi-server support (Plex, Jellyfin, and Emby all work from the one codebase now) plus a few Jellyseerr-exclusive features like PostgreSQL support and DNS caching. If you're starting fresh, install Seerr directly rather than either legacy project, existing Overseerr/Jellyseerr installs can migrate to it (the project's own migration guide covers the steps, including a Docker volume path change for anyone using PostgreSQL).

### Related
[[Media Management (Arr Stack)]] [[Radarr]] [[Sonarr]] [[Plex]] [[Jellyfin]]
