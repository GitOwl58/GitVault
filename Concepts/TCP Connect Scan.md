#domain/pentesting #domain/networking

# TCP Connect Scan

A **[[Port Scan]]** type (`nmap -sT`) that completes the full [[Three-way handshake]] with every target port. If a port is open, Nmap finishes the handshake and then tears the connection down with a TCP RST-ACK; a closed port replies RST-ACK immediately, without the handshake ever completing. Functionally the same as what a `telnet` client does one port at a time, just automated across the whole range. Because it fully opens each connection, it's noisier and more likely to be logged than a **[[SYN Scan]]**.

### Related
[[Port Scan]] [[SYN Scan]] [[Three-way handshake]] [[TCP Flags]] [[Nmap]]

### Source:
[[18. Nmap The Basics]]
