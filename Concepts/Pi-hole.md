#domain/homelab

# Pi-hole

A network-wide ad and tracker blocker that works by acting as a **DNS** sinkhole: it runs as the DNS server for the network (either directly, or as the upstream DNS the router hands out via **[[DHCP]]**), and when a device asks to resolve a known ad/tracking domain, Pi-hole simply refuses to resolve it instead of forwarding the request on. The ad or tracker's request never leaves the device, which blocks ads and trackers across every device on the network at once, phones, smart TVs, IoT gadgets, without installing anything on each one individually.

Despite the name, it doesn't require a Raspberry Pi specifically, it's a lightweight service that runs happily as one more container in any homelab stack. It ships with a web dashboard showing query stats and lets you manage blocklists and whitelist specific domains that get caught by mistake.

### A few practical notes
- Because it becomes a single point of failure for DNS resolution, running a second Pi-hole instance (with keepalived or a similar failover setup) avoids the whole network losing DNS if the one instance goes down.
- Pi-hole blocks at the DNS level, so it won't catch ads embedded in a page's own first-party domain (some YouTube ads, for example), a browser-based blocker still helps for those.
- Regularly updating blocklists (Pi-hole supports subscribing to community-maintained lists) keeps it effective as ad networks rotate domains.

### Related
[[Homelab Hardware Tiers]] [[Self-Hosted Service Stack]] [[DHCP]] [[Homelab Networking Basics]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
