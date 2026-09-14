#domain/os

# Rsync

An open-source file-sync/backup tool that transfers only the changed parts of a file rather than the whole thing, making it efficient for large datasets over a network. `rsync -av <source> <dest>` preserves permissions/timestamps (`-a`) with verbose output (`-v`); `-z` adds compression, `--backup --backup-dir=<dir>` keeps incremental copies, `--delete` mirrors deletions. Routing it through `-e ssh` (`rsync -avz -e ssh ...`) encrypts the transfer over an **[[SSH]]** tunnel. Commonly paired with **[[Cron]]** for scheduled, unattended backups.

### Related
[[SSH]] [[Cron]]

### Source:
[[20. Backup and Restore]]
