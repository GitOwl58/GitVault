#domain/networking

# NFS

Network File System: lets remote directories appear and behave like local ones, used for centralized file management across Linux (and Windows) hosts. Configured via `/etc/exports` (Linux) with access options like `rw`/`ro`, `no_root_squash` (client's root keeps root rights, dangerous), `root_squash` (downgrades it), and `sync`/`async` (commit-before-vs-after-ack). A client mounts a share with `mount <host>:/path <mountpoint>`. Misconfigured shares (especially `no_root_squash`) are a known Linux privilege-escalation vector. Solaris has its own NFS implementation, configured via `share -F nfs` and `/etc/dfs/dfstab`.

n a homelab
The standard way homelab compute hosts reach shared storage on a **[[NAS]]**, rather than storing large amounts of data locally on each host. On the client:
```bash
apt install nfs-common
mkdir /nas
```
Add a persistent entry to `/etc/fstab`:
```
192.168.1.50:/volume1/media  /nas  nfs  defaults  0  0
```
Then:
```bash
systemctl daemon-reload
mount /nas
```
Worth restricting the export to the homelab's own subnet in `/etc/exports` rather than leaving it open to the whole network, and simpler to set up than SMB for a Linux-only environment, SMB (Samba) is the better choice when Windows/macOS clients need the same share. See **[[Self-Hosted Service Stack]]** and **[[Homelab Setup]]**.

### Related
[[SSH]] [[File System]] [[NAS]] [[Self-Hosted Service Stack]] [[Homelab Networking Basics]]

### Source:
[[18. Network Services]]
[[28. Solaris]]
Homelab additions synthesized from external homelab guides, not a course lesson, drafted for review before merging into the vault (this note already exists in the vault under `Concepts/NFS.md`, this version merges the existing course content with the homelab additions, drop-in replacement rather than a fresh file).

