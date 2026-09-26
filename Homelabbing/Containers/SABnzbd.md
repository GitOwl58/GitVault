#domain/homelab

# SABnzbd

A Usenet downloader, the equivalent role to **[[qBittorrent]]** but for Usenet/NZB-based indexers instead of torrents. Requires a paid Usenet provider subscription and (usually) a separate indexer to search NZBs, but in exchange offers generally faster, more consistent download speeds than torrenting, since it's pulling from provider servers rather than depending on how many peers are seeding.

Plugs into the Arr stack the same way qBittorrent does, **[[Sonarr]]**/**[[Radarr]]**/**[[Readarr]]** send it jobs and watch a completed-downloads folder for the finished result.

### Related
[[Media Management (Arr Stack)]] [[qBittorrent]] [[Prowlarr]]
