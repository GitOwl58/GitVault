#domain/homelab

# Minecraft Server

A self-hosted Minecraft (Java or Bedrock edition) server, frequently one of the first genuinely "useful" containers someone runs on a new homelab, easy to explain to family or friends, and a low-stakes way to practice real homelab skills: port forwarding, resource limits (a Minecraft server can happily eat all available RAM if not capped), backups (world data corrupts or gets griefed, and a recent backup is the only real recovery plan), and basic uptime monitoring.

Common Docker images (like `itzg/minecraft-server`) handle most of the setup through environment variables, version, server type (Vanilla, Paper, Forge for mods), memory limits, rather than manual server.properties editing.

### Related
[[Miscellaneous]] [[Homelab Backups and Maintenance]] [[Homelab Networking Basics]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
