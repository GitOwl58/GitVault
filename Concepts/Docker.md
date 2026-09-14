#domain/os #domain/pentesting

# Docker

An open-source containerization platform: packages an application plus its dependencies as a self-contained image, run as an isolated **[[Container]]**, using a layered filesystem and kernel resource isolation. Images come from Docker Hub (public/private registries) or are built locally from a **Dockerfile** (a list of build steps: base image via `FROM`, package installs, user setup, exposed ports, startup command via `CMD`). `docker build -t <tag> .` builds an image; `docker run -p <host>:<container> -d <image>` runs it. Containers are immutable at runtime; permanent changes require rebuilding the image. Compared to **[[LXC]]**, Docker trades some low-level control for a friendlier, more portable, more secure-by-default workflow.

### Related
[[Container]] [[LXC]]

### Source:
[[22. Containerization]]
