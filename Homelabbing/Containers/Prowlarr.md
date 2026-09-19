#domain/homelab

# Prowlarr

Centralized indexer management for the whole Arr stack. Instead of configuring the same set of torrent/Usenet indexers separately inside **[[Sonarr]]**, **[[Radarr]]**, and **[[Readarr]]**, you configure them once in Prowlarr and it syncs them out to each app automatically. Also handles indexer health checks and, for torrent indexers, can manage tracker-specific settings centrally.

Effectively the plumbing layer that makes the rest of the Arr stack less repetitive to set up and maintain, install it early, before the individual Arr apps, to avoid reconfiguring indexers multiple times.

### Related
[[Media Management (Arr Stack)]] [[Sonarr]] [[Radarr]] [[Readarr]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
