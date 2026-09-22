#domain/homelab

# Homelab Common Mistakes

A consolidated list of the mistakes that show up across homelab guides and forums, most of them happen in the first six months, and most of them are avoidable with a bit of discipline/analysis... 

### Planning and documentation
- **Not documenting anything.** Six months later, nobody remembers why a container was set up a certain way, what a specific IP was for, or what a firewall rule does. Even a simple running notes file (fittingly, in a vault like this one) saves hours later.
- **Poor network planning.** Sketch/map the network, even roughly, before wiring things up. Retrofitting VLANs or renumbering subnets after the fact is far more painful than planning them from the start.
- **Overlapping IP ranges.** Especially relevant if running a VPN back into the homelab from another network (a phone's hotspot, another site), overlapping private ranges cause confusing, hard-to-diagnose routing failures.

### Setup habits
- **Installing everything at once.** Spinning up 20 services over a weekend means 20 things that can break at once, with no way to isolate which change caused the problem. Add services incrementally.
- **Not setting static IPs (or DHCP reservations) early.** A server whose IP changes on reboot breaks every other service pointing at it. Do this before anything depends on the address.
- **Changing settings without understanding them, or copying firewall/router rules from a random YouTube video** without knowing what they actually do. Either one can silently open something to the internet that shouldn't be, or simply slow down the learning process, any code ran on the terminal should be understood...
- **Running everything as root** inside containers/VMs by default, when a dedicated low-privilege user could, unnecessarily widens the blast radius.

### Resource and risk management
- **Overcommitting RAM** across VMs/containers on a single host, assuming every VM will use its full allocation at once causes host-level instability under real load.
- **Not monitoring resources**, so a slowly filling disk or a runaway process goes unnoticed until something actually fails.
- **Skipping backups**, or having backups that were never actually tested with a real restore. See **[[Homelab Backups and Maintenance]]** for the 3-2-1 rule and concrete scripts.
- **Not snapshotting before changes.** A snapshot takes seconds; recovering from a bad update without one can take hours.

### Security
- **Exposing services to the internet without segmentation.** If anything is internet-facing, put it on its own **VLAN**, isolated from personal devices and the rest of the homelab, so a compromise there doesn't spread.
- **Preferring VMs over containers "just in case."** Containers are usually sufficient and lighter for most self-hosted Linux services; reach for a full VM specifically when strong isolation or a non-Linux OS is actually needed, not by default.
- **Forgetting Plex's remote-streaming paywall change** when planning a media setup, if the goal is free remote access, Jellyfin avoids the surprise later (see **[[Self-Hosted Service Stack]]**).

### The general theme
Almost every item above comes down to the same root cause: moving faster than the understanding of what's actually being changed. Slowing down slightly, documenting as you go, and changing one thing at a time resolves most of this list on its own.

### Related
[[Homelab Setup]] [[Homelab Backups and Maintenance]] [[Homelab Networking Basics]] [[Self-Hosted Service Stack]] [[RAID]] [[NAS]]

### Source:
Synthesized from external homelab guides and my homelab setup.

