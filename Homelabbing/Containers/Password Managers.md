#domain/homelab

# Password Managers

Self-hosting a password manager keeps the encrypted vault under your own roof instead of a third-party's cloud, while still getting the same browser extensions, mobile apps, and autofill experience as a commercial one.

### Options
- **[[Vaultwarden]]**: by far the default choice, a lightweight reimplementation of the Bitwarden server that's compatible with all official Bitwarden client apps.
- **Bitwarden's own official self-hosted server**: exists too, but is heavier (a multi-container stack) and mainly aimed at organizations, most homelabbers use Vaultwarden instead for exactly this reason.

### A word of caution
A password manager is one of the few homelab services where downtime or a mistake actually hurts, if it's unreachable, you're locked out of everything else. Keep backups of its data directory current and tested (see **[[Homelab Backups and Maintenance]]**), and think carefully before exposing it directly to the internet without a **[[Reverse Proxy]]** and strong 2FA.

### Related
[[Vaultwarden]] [[Self-Hosted Service Stack]] [[Homelab Backups and Maintenance]] [[Reverse Proxy]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
