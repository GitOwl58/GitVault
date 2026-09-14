#domain/os #domain/pentesting

# LXC

Linux Containers: virtualizes multiple isolated Linux systems on one host using kernel resource-isolation features: **cgroups** (resource limits: CPU shares, memory caps) and **namespaces** (isolated PID, network, and mount views per container). Images are built manually (a root filesystem plus installed packages) rather than from a Dockerfile, so LXC containers are less portable and need more expertise than **[[Docker]]**, though both sit on the same underlying kernel features. Managed via `lxc-create`, `lxc-start`/`lxc-stop`, `lxc-attach`, with resource limits set per-container in `/usr/share/lxc/config/<name>.conf`.

### Related
[[Docker]] [[Container]]

### Source:
[[22. Containerization]]
