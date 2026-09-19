#domain/homelab

# RAID

**Redundant Array of Independent Disks**, a way of combining multiple physical drives into one logical volume, for some mix of better performance, redundancy against drive failure, or both, depending on the RAID level chosen.

### Common levels for a homelab
- **RAID 0**: stripes data across drives for speed, zero redundancy, one drive failing loses everything. Rarely the right call for a homelab NAS.
- **RAID 1**: mirrors data across two drives, full redundancy, only 50% usable capacity. Simple and safe for small setups.
- **RAID 5**: stripes data with one drive's worth of parity, survives one drive failure, better capacity efficiency than RAID 1. The common baseline for a home NAS with 4+ drives.
- **RAID 6**: like RAID 5 but with two parity drives, survives two simultaneous failures, worth it for larger arrays where rebuild time (and the risk of a second failure during rebuild) is a real concern.
- **RAID 10**: mirrored pairs striped together, fast and redundant, but only 50% usable capacity like RAID 1.

### The one thing worth repeating
**RAID is not a backup.** It protects against a drive dying, not against accidental deletion, ransomware, a bad update, or the NAS itself being destroyed (fire, flood, theft). The 3-2-1 rule still applies on top of RAID, not instead of it, see **[[Homelab Backups and Maintenance]]**.

### Software vs hardware RAID
A dedicated RAID controller card handles the RAID logic in hardware, common on used enterprise servers. Software RAID (mdadm on Linux, or **[[ZFS]]**'s own RAIDZ) does the same job in the OS, more flexible and easier to recover from without matching hardware, and increasingly the more recommended approach for a homelab.

### Related
[[NAS]] [[ZFS]] [[Homelab Backups and Maintenance]] [[Homelab Hardware Tiers]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
