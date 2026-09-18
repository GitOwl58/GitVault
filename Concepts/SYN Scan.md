#domain/pentesting #domain/networking

# SYN Scan

A **[[Port Scan]]** type (`nmap -sS`), also called a "stealth scan". Sends only the initial SYN packet instead of completing the **[[Three-way handshake]]**: an open port replies SYN-ACK, but Nmap answers with RST rather than finishing the handshake, so a full connection is never actually established. This produces fewer logs than a **[[TCP Connect Scan]]**, making it the quieter default choice, at the cost of needing raw-socket access (root).

### Related
[[Port Scan]] [[TCP Connect Scan]] [[Three-way handshake]] [[TCP Flags]] [[Nmap]]

### Source:
[[18. Nmap The Basics]]
