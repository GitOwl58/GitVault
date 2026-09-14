#domain/os #domain/security

# sudo

Executes a single command as another user (root by default), governed by rules in `/etc/sudoers`. Preferred over logging in as root outright or using `su` (which switches the whole shell session) because it follows least-privilege: a user can be granted just the specific commands they need as root rather than blanket root access.

### Related
[[Permissions]]

### Source:
[[14. User Management]]
[[25. Linux Security]]
