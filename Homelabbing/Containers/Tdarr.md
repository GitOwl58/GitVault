#domain/homelab

# Tdarr

Automated media transcoding across a whole library, useful for standardizing a mixed-format library (different codecs, containers, bitrates accumulated over time) into one consistent, space-efficient format, or for offloading transcoding work from the media server itself by pre-converting files instead of transcoding on the fly for every playback.

Supports distributed processing (multiple "node" workers, potentially across several machines) for large libraries, and hardware-accelerated encoding (Intel Quick Sync, NVENC) when the host supports it, which matters a lot for how long a full library re-encode actually takes.

### Related
[[Media Management (Arr Stack)]] [[Self-Hosted Service Stack]] [[Proxmox]]
