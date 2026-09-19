#domain/os #domain/pentesting

# LXC

Linux Containers: virtualizes multiple isolated Linux systems on one host using kernel resource-isolation features: **cgroups** (resource limits: CPU shares, memory caps) and **namespaces** (isolated PID, network, and mount views per container). Images are built manually (a root filesystem plus installed packages) rather than from a Dockerfile, so LXC containers are less portable and need more expertise than **[[Docker]]**, though both sit on the same underlying kernel features. Managed via `lxc-create`, `lxc-start`/`lxc-stop`, `lxc-attach`, with resource limits set per-container in `/usr/share/lxc/config/<name>.conf`.

### In a homelab
**[[Proxmox]]** uses LXC as one of its two main workload types alongside full KVM VMs, behaving much more like a lightweight whole Linux system (its own init, services, filesystem) than a Docker container does. The common Proxmox pattern is one LXC container per major service or service group, for stronger isolation and independent snapshotting than running everything in one place, sometimes with Docker running inside the LXC container itself, layering both approaches. See **[[Homelab Setup]]**.

### Related
[[Docker]] [[Container]] [[Proxmox]] [[VM]] [[Hypervisor]] [[Homelab Setup]]

### Source:
[[22. Containerization]]
Homelab additions synthesized from external homelab guides, not a course lesson, drafted for review before merging into the vault (this note already exists in the vault under `Concepts/LXC.md`, this version merges the existing course content with the homelab additions, drop-in replacement rather than a fresh file).

