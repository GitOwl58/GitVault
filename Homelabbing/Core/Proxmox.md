#domain/homelab

# Proxmox

I do not use Proxmox (yet), as I personally find joy in running Docker containers, on a Debian server, it is minimalist, reliable, and my homelab usage so far does not require such architecture... Plus I do enjoy building my own network, doing my updates, etc.
But I cover it on it's own full size note as it is very talked about recently, and maybe something I will come to use some day.

**Proxmox VE** (Virtual Environment) is a free, open-source virtualization platform built on **KVM** (full VMs) and **[[LXC]]** (lightweight OS-level containers), the default most homelabbers converge on after outgrowing plain **[[Docker]]**. As of late 2026 the current stable branch is **Proxmox VE 9.2** (released in May 2026), running on kernel 7.0.

### Why it's the common default
- **Web UI**: manage VMs, containers, storage, and networking from a browser, no CLI required for day-to-day use, though the CLI is there when needed.
- **Snapshots and rollback**: take a snapshot before any risky change, roll back instantly if it breaks something. This alone removes most of the fear around experimenting.
- **ZFS integration**: built-in support for ZFS pools, giving checksummed storage, easy snapshots at the filesystem level, and replication between hosts.
- **Clustering**: multiple Proxmox hosts can be joined into a cluster, enabling live migration of VMs between hosts and, eventually, high availability.
- Free and open-source, a paid support subscription exists but isn't required for home use.
- **Actively developed**: recent 9.x releases added a Dynamic Load Balancer for HA clusters (automatically rebalances VMs across nodes based on real-time load), expanded Software-Defined Networking with WireGuard and BGP fabrics for more advanced multi-site setups, and even early ARM64 support, none of which a typical single-node homelab needs immediately, but it shows the project isn't standing still.

### VMs vs containers, in Proxmox terms
A **KVM VM** is a full virtual machine, its own kernel, full OS, strongest isolation, needed for anything that isn't Linux (Windows, BSD) or needs kernel-level access. An **LXC container** shares the host's kernel, starts in seconds, uses a fraction of the RAM/CPU overhead of a VM, and is the default choice for most self-hosted Linux services. The common pattern: one LXC container per service, so each one can be updated, snapshotted, and restarted independently without affecting the others.

### Basic CLI examples
Creating and starting a VM from the command line (the web UI does the same thing under the hood):
```bash
qm create 100 --name myvm --memory 2048 --cores 2 --net0 virtio,bridge=vmbr0
qm set 100 --ide2 local:iso/ubuntu-22.04.iso,media=cdrom
qm start 100
```

A basic network bridge configuration in `/etc/network/interfaces`, giving the host a static IP on the LAN:
```
auto vmbr0
iface vmbr0 inet static
    address 192.168.1.10/24
    gateway 192.168.1.1
    bridge-ports eno1
    bridge-stp off
    bridge-fd 0
```

### Alternatives
Proxmox isn't the only option, and the right choice depends on what matters most:
- **Unraid** (one-time license, tiers roughly €45-50 Starter / €100-105 Unleashed / €230-240 Lifetime, converted from current USD pricing, check Unraid's own site for exact EU/VAT pricing): polished UI, huge app-store-style plugin ecosystem, very friendly for storage/media-focused setups, but paid, and pricier than it used to be after a 2024 licensing overhaul.
- **TrueNAS Scale**: free, **[[ZFS]]**-focused, best when the primary job is **[[NAS]]**/storage with virtualization as a secondary feature rather than the main point.
- **CasaOS**: free, the simplest of the bunch, Docker-only (no VM/container virtualization layer), a good fit for a single-purpose, low-complexity box.
- **Bare Ubuntu/Debian + Docker**: the DIY route, no hypervisor layer at all, maximum control and minimum abstraction, at the cost of doing everything (networking, storage, updates) by hand.

Proxmox sits in the middle: more capable than a Docker-only OS, more approachable than a fully bare-metal DIY setup.

### Related
[[Homelab Setup]] [[Homelab Hardware Tiers]] [[Container]] [[LXC]] [[Docker]] [[VM]] [[Hypervisor]] [[ZFS]] [[NAS]]

### Source:
Compiled data from external homelab guides, will be updated, checked for errors regularly...
