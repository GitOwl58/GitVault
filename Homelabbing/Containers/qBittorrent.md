#domain/homelab

# qBittorrent

A free, open-source BitTorrent client, the most common download client wired into the Arr stack for torrent-based indexers. Has a solid web UI (useful for headless/container use, since there's no desktop to open) and built-in support for categories, so **[[Sonarr]]**/**[[Radarr]]** can tell it exactly where to place a download and pick it up automatically once finished.

Often run behind a VPN container (policy-routed so only qBittorrent's traffic goes through the tunnel) when downloading torrents, worth deciding deliberately rather than skipping, depending on what's actually being downloaded and local regulations.

### Related
[[Media Management (Arr Stack)]] [[SABnzbd]] [[Sonarr]] [[Radarr]]
