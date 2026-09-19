#domain/homelab

# ZFS

A combined filesystem and volume manager (originally from Solaris, now widely used on Linux and BSD via OpenZFS) built with data integrity as its core design goal. Every block written gets a checksum, and ZFS verifies that checksum on every read, silently catching and, with redundancy, correcting **bit rot** (slow data corruption on disk) that a traditional filesystem would never notice.

### Why homelabbers reach for it
- **Snapshots**: near-instant, space-efficient point-in-time copies of a filesystem, the basis for fast backups and easy rollback.
- **RAID-like redundancy built in** (RAIDZ1/RAIDZ2/RAIDZ3, roughly comparable to RAID5/6 but integrated into the filesystem itself rather than a separate layer), protecting against drive failure without a separate hardware RAID controller.
- **Replication**: snapshots can be sent incrementally to another ZFS pool, locally or over the network, a clean way to keep an offsite backup in sync.
- **Compression and deduplication**, often reducing actual disk usage for compressible data at very low CPU cost.

### The tradeoff
ZFS wants **ECC RAM** for maximum protection against memory-corruption-caused data loss (it will run fine without ECC, the risk is often overstated for home use, but it's the reason it comes up in every ZFS discussion), and it's more resource-hungry than a simple filesystem, mainly RAM for its caching layer. **Proxmox** and **TrueNAS Scale** both offer ZFS as a first-class storage option, making it accessible without manual setup.

### Related
[[NAS]] [[RAID]] [[Proxmox]] [[Homelab Backups and Maintenance]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
