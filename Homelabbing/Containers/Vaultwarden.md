#domain/homelab

# Vaultwarden

A lightweight, unofficial reimplementation of the Bitwarden server, written in Rust, that's fully compatible with all the official Bitwarden client apps (browser extensions, mobile, desktop). This is the near-universal choice for self-hosting a password manager, since it gets the same clients and autofill experience as the commercial product while running as a single small container instead of Bitwarden's own much heavier official self-hosted stack.

### Practical notes
- Needs HTTPS to work properly with browser extensions, almost always run behind a **[[Reverse Proxy]]** for that reason.
- Supports the same feature set most people actually use: vaults, folders, TOTP-based 2FA storage, secure notes, and organization/sharing between accounts.
- Back its data directory up like nothing else in the stack matters more, see **[[Password Managers]]** for why.

### Related
[[Password Managers]] [[Reverse Proxy]] [[Homelab Backups and Maintenance]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
