#domain/networking

# NFS

Network File System: lets remote directories appear and behave like local ones, used for centralized file management across Linux (and Windows) hosts. Configured via `/etc/exports` (Linux) with access options like `rw`/`ro`, `no_root_squash` (client's root keeps root rights, dangerous), `root_squash` (downgrades it), and `sync`/`async` (commit-before-vs-after-ack). A client mounts a share with `mount <host>:/path <mountpoint>`. Misconfigured shares (especially `no_root_squash`) are a known Linux privilege-escalation vector. Solaris has its own NFS implementation, configured via `share -F nfs` and `/etc/dfs/dfstab`.

### Related
[[SSH]] [[File System]]

### Source:
[[18. Network Services]]
[[28. Solaris]]
