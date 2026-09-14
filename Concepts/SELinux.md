#domain/security

# SELinux

Security-Enhanced Linux: a Mandatory Access Control (MAC) system built directly into the Linux kernel. Every process, file, directory, and system object gets a security label; policy rules control access between labeled objects, enforced by the kernel, enabling very granular control (e.g. who can append to vs. move a file). More powerful but more complex to configure than **[[AppArmor]]**, its lighter-weight alternative.

### Related
[[AppArmor]] [[TCP Wrappers]] [[Permissions]]

### Source:
[[23. Network Configuration]]
[[25. Linux Security]]
