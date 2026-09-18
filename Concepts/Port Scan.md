#domain/pentesting #domain/networking

# Port Scan

Probing a host's TCP/UDP ports to find out which ones have a service listening, the second half of what [[Nmap]] does after host discovery. Three main types: **[[TCP Connect Scan]]** (`-sT`, completes the full handshake), **[[SYN Scan]]** (`-sS`, stops after the SYN, quieter), and **[[UDP Scan]]** (`-sU`, connectionless, relies on ICMP replies to infer closed ports). By default a scan covers the 1000 most common ports; `-F` narrows that to 100, `-p[range]` sets an explicit range, and `-p-` covers all 65,535.

### Related
[[TCP Connect Scan]] [[SYN Scan]] [[UDP Scan]] [[Nmap]] [[Ports]] [[TCP]] [[UDP]]

### Source:
[[18. Nmap The Basics]]
