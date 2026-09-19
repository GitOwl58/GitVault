#domain/homelab

# NAS

**Network-Attached Storage**, a dedicated device (or a role a server plays) that holds data centrally and shares it with other machines over the network, rather than storing it locally on each device. In a homelab, the NAS is usually where the actual data lives: media libraries, documents, backups, container config, while compute hosts (Proxmox, mini PCs) mount that storage over **[[NFS]]** or SMB rather than keeping large amounts of data on their own disks.

A NAS can be a purpose-built appliance (Synology, QNAP), or simply a server/VM running NAS software (TrueNAS Scale, Unraid, or a bare Linux box with **[[ZFS]]**/**[[RAID]]** and NFS/Samba configured). Dedicated NAS appliances trade flexibility for a much simpler setup and management UI; a DIY NAS trades some convenience for full control and usually better price-per-terabyte.

### Why it matters for a homelab
Centralizing storage on a NAS means compute hosts stay disposable, if a Proxmox host dies, only the containers/VMs need rebuilding, the actual data never lived there in the first place. It also makes the **3-2-1 backup rule** easier to apply, since there's one clear place data actually lives, rather than scattered across every service's own container.

### Related
[[NFS]] [[RAID]] [[ZFS]] [[Homelab Setup]] [[Self-Hosted Service Stack]] [[Homelab Backups and Maintenance]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
