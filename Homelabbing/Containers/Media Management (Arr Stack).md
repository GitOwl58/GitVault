#domain/homelab

# Media Management (Arr Stack)

The "Arr" apps are a family of automation tools that, together, turn a media server from "manually drop files in a folder" into "search for a show, click request, it appears." Each one owns one job and hands off to the next, which is why they're almost always run as a set rather than individually.

### The pipeline
1. **[[Seerr]]** (or a client app) is where a request comes in ("add this movie").
2. **[[Sonarr]]** / **[[Radarr]]** / **[[Readarr]]** decide what to actually grab (TV, movies, books respectively) and hand the search off to an indexer.
3. **[[Prowlarr]]** manages indexers centrally so Sonarr/Radarr/Readarr don't each need their own separate configuration.
4. **[[qBittorrent]]** or **[[SABnzbd]]** does the actual downloading.
5. **[[Bazarr]]** fetches matching subtitles automatically.
6. **[[Tdarr]]** optionally re-encodes files after the fact for consistency or smaller size.
7. **[[Tautulli]]** and **[[Audiobookshelf]]** round out the stack: usage stats for Plex, and a dedicated player/server for audiobooks.

This is the part of a homelab most guides warn about installing all at once (see **[[Homelab Common Mistakes]]**), add one piece, get it working end to end, then add the next.

### Related
[[Media Servers]] [[Self-Hosted Service Stack]] [[Homelab Common Mistakes]]
