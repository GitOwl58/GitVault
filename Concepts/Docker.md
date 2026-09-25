#domain/cloud-virtualisation #domain/pentesting

# Docker

An open-source containerization platform: packages an application plus its dependencies as a self-contained image, run as an isolated **[[Container]]**, using a layered filesystem and kernel resource isolation. Images come from Docker Hub (public/private registries) or are built locally from a **Dockerfile** (a list of build steps: base image via `FROM`, package installs, user setup, exposed ports, startup command via `CMD`). `docker build -t <tag> .` builds an image; `docker run -p <host>:<container> -d <image>` runs it. Containers are immutable at runtime; permanent changes require rebuilding the image. Compared to **[[LXC]]**, Docker trades some low-level control for a friendlier, more portable, more secure-by-default workflow.

### In a homelab
Docker (with **[[Docker Compose]]** for multi-container stacks) is the near-universal packaging format for self-hosted services, one container per service is the standard pattern, so each app updates, restarts, and snapshots independently. See **[[Homelab Setup]]** and **[[Self-Hosted Service Stack]]** for the fuller picture of what actually gets run this way.

### Related
[[Container]] [[LXC]] [[Docker Compose]] [[Homelab Setup]] [[Self-Hosted Service Stack]]

### Source:
[[22. Containerization]]
Homelab additions synthesized from external homelab guides, not a course lesson, drafted for review before merging into the vault (this note already exists in the vault under `Concepts/Docker.md`, this version merges the existing course content with the homelab additions, drop-in replacement rather than a fresh file).
