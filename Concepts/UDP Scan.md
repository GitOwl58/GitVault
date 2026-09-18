#domain/pentesting #domain/networking

# UDP Scan

A **[[Port Scan]]** type (`nmap -sU`). [[UDP]] has no handshake to complete, so Nmap just sends a probe: a closed port typically answers with an [[ICMP]] "Destination Unreachable (port unreachable)", while an open one often just stays silent, since UDP carries no obligation to acknowledge anything. That ambiguity makes UDP scans slower and less certain to interpret than TCP scans. Worth running against common UDP services: DNS, DHCP, NTP, SNMP, VoIP.

### Related
[[Port Scan]] [[UDP]] [[ICMP]] [[Nmap]] [[DNS]] [[DHCP]]

### Source:
[[18. Nmap The Basics]]
