#domain/homelab

# Homelab Backups and Maintenance

A homelab without backups isn't a lab, it's a liability, and the second most repeated piece of advice across every homelab guide (after "start small") is to back things up from day one, not after the first real loss.

### The 3-2-1 rule
Keep **3** copies of important data, on **2** different types of media, with **1** copy offsite. In practice for a homelab: the live data on the **[[NAS]]**/server (ideally itself on **[[RAID]]** or **[[ZFS]]** for drive-failure protection, though RAID/ZFS is not a backup on its own, it protects against disks dying, not against accidental deletion, ransomware, physical degradation...), a second copy on a different physical drive or NAS, and a third copy either in the cloud (Providers like Hetzner Storage Box or a privacy-focused option are common choices for EU) or physically at another location (a family member's house, a work location, etc). Losing the live copy should never mean losing the data.

### Proxmox snapshots and vzdump
Snapshots capture a VM/container's state instantly, useful before any risky change (an update, a config edit) so a bad outcome is one click away from undone. A full backup (`vzdump`) is heavier but portable, it captures the entire VM/container to a file that can be restored on different hardware entirely:
```bash
vzdump 100 --storage local --mode snapshot --compress zstd
```

### Backing up Docker volumes
A simple pattern using a throwaway Alpine container to tar a volume's contents out to the host:
```bash
docker run --rm \
  -v sonarr_config:/data \
  -v $(pwd)/backups:/backup \
  alpine tar czf /backup/sonarr_config_$(date +%Y%m%d).tar.gz -C /data .
```

### An automated backup script (skeleton)
```bash
#!/bin/bash
TIMESTAMP=$(date +%Y%m%d_%H%M%S)
BACKUP_DIR="/backups/$TIMESTAMP"
mkdir -p "$BACKUP_DIR"

echo "[$TIMESTAMP] Starting backup" >> /var/log/homelab-backup.log

# back up whatever matters: vzdump calls, docker volume tars, config file copies, etc.

# retention: delete backups older than 14 days
find /backups -maxdepth 1 -type d -mtime +14 -exec rm -rf {} \;

echo "[$TIMESTAMP] Backup complete" >> /var/log/homelab-backup.log

# optional: notify on completion or failure
# curl -X POST -H 'Content-type: application/json' \
#   --data '{"text":"Homelab backup completed"}' "$SLACK_WEBHOOK_URL"
```
Run it on a schedule with `cron`, and actually test a restore occasionally, an untested backup is only a hypothesis.

### An automated update script (skeleton)
```bash
#!/bin/bash
apt update && apt upgrade -y

cd /opt/stacks/media && docker compose pull && docker compose up -d
cd /opt/stacks/infra && docker compose pull && docker compose up -d

# if running k3s/Kubernetes anywhere:
# kubectl get nodes
```
Snapshot before running this, not after, so a bad update is a rollback, not a rebuild.

### Monitoring
Keeping an eye on what's running matters as much as backing it up. **Uptime Kuma** gives simple, clean uptime/status checks for services. **Prometheus + Grafana + Node Exporter** gives deeper host and container-level metrics and dashboards. Heavier alternatives exist for larger or more enterprise style setups: **Zabbix** and **Checkmk RAW** (free), both more complex to set up but more full-featured for large environments.

### Troubleshooting cheat-sheet
| Command                              | Use                                       |
| ------------------------------------ | ----------------------------------------- |
| `docker logs <name_of_container>`    | Read a container's logs                   |
| `docker stats`                       | Live CPU/RAM usage per container          |
| `docker system prune -a`             | Clean up unused images/containers/volumes |
| `ping <host>`                        | Basic reachability check                  |
| `nslookup <domain>` / `dig <domain>` | DNS resolution check                      |
| `ufw status` / `iptables -L`         | Check firewall rules                      |
| `htop` (or btop if installed)        | Live process/CPU/RAM view                 |
| `free -h`                            | RAM usage summary                         |
| `df -h`                              | Disk space usage                          |
| `iotop`                              | Disk I/O by process                       |
| `nethogs`                            | Network usage by process                  |

### Related
[[Homelab Setup]] [[Proxmox]] [[Docker]] [[Self-Hosted Service Stack]] [[NAS]] [[RAID]] [[ZFS]]

### Source:
Synthesized from external homelab guides and my homelab setup.
