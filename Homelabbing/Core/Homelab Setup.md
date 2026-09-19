#domain/homelab

# Homelab Setup

My homelab is a sandbox: a place to run real infrastructure at home so I can learn, break things, and rebuild them. I'm not attracted to the hardware, but trying something new on production always ends badly, so I build myself a safe place to fail instead.

This note is the practical "how to actually build one" hub. For the short general definition, see the existing **[[Homelab]]** concept note, which already links forward to this note (as `[[Homelab setup]]`, a link that resolves to this file once it's added to the vault).

The pattern that shows up across almost every homelab, regardless of budget: a **[[Router]]**/**[[Firewall]]** at the edge, a **[[Switch]]** to tie devices together, one or more **[[Hypervisor]]** hosts running **[[Container]]**s or VMs, and a **[[NAS]]** or dedicated storage box holding the actual data. Everything else (media servers, ad blockers, monitoring, home automation) is a service layered on top of that base.

### This note is the hub, see:
- **[[Homelab Hardware Tiers]]**: what to actually buy, at every budget from €0 to €1000+
- **[[Homelab Physical Setup]]**: where to put it, racks vs cabinets, power, cooling, cabling
- **[[Proxmox]]**: the virtualization platform almost everyone converges on, and the alternatives
- **[[Homelab Networking Basics]]**: routers, switches, IP addressing, subnetting, segmentation, recap for the homelab context
- **[[Self-Hosted Service Stack]]**: what to actually run, Docker Compose examples, the "one service per container" philosophy, mounting NAS storage, and a map into the `Containers/` subfolder's per-app notes
- **[[Homelab Backups and Maintenance]]**: the 3-2-1 rule, snapshots, monitoring, update/backup automation
- **[[Homelab Common Mistakes]]**: the stuff that bites almost everyone in the first six months

---
### Start small
The single most repeated advice across every homelab writeup: don't overthink the first build. You don't need a rack, 10G networking, or ECC RAM on day one. A used office PC or even an old laptop with **[[Docker]]** on it is enough to learn the fundamentals. Upgrade when you hit an actual limitation, a slow transcode, running out of RAM, needing more drive bays, not before, based on a limitation you imagine you'll have.

A homelab is meant to grow with you. Typical arc: single cheap machine running a handful of containers → get used to run, maintain, troubleshoot your first issues → a proper NAS for storage → a dedicated hypervisor host → a second host and clustering → VLANs and a real firewall once something is exposed to the internet → monitoring and automation once there's enough to keep track of. 
Or maybe stay at Stage 1, just running a cheap machine because all you want is a media server, a password manager, and you are not interested in Proxmox, VMs, etc etc...

### Why it's worth it
Beyond the skills (Linux, Docker, networking, virtualization), a homelab teaches troubleshooting under real constraints in a way tutorials can't: something breaks, you don't know why, and you have to actually figure it out. It also tends to pay for itself in avoided subscriptions as long as you don't all in on a professional-grade brand new server and 100 TB storage (media server instead of streaming fees, self-hosted password manager, ad blocking, etc.), though that's a side benefit, not really the point.

### Related  ///Module is not finished, many deadlinks linking to contents in a draft folder///
[[Homelab]] [[Homelab Hardware Tiers]] [[Homelab Physical Setup]] [[Proxmox]] [[Homelab Networking Basics]] [[Self-Hosted Service Stack]] [[Homelab Backups and Maintenance]] [[Homelab Common Mistakes]] [[Docker]] [[Docker Compose]] [[Container]] [[LXC]] [[Router]] [[Switch]] [[Firewall]] [[NAS]] [[Hypervisor]]

### Source:
Compiled data from external homelab guides, will be updated, checked for errors regularly...
