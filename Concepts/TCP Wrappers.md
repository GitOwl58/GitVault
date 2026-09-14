#domain/security

# TCP Wrappers

A host-based network access-control mechanism: restricts which client IPs/hostnames can reach a given service, checked against `/etc/hosts.allow` (grant) and `/etc/hosts.deny` (deny) before the connection is handed to the service. Rules are evaluated in order, first match wins. Controls *service* access only, not ports, so it complements rather than replaces a real **[[Firewall]]**.

### Related
[[Firewall]] [[SELinux]] [[AppArmor]]

### Source:
[[23. Network Configuration]]
[[25. Linux Security]]
