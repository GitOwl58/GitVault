#type/concept #domain/networking

# DHCP (Dynamic Host Configuration Protocol)

Automatically assigns an [[IP address]] to a device joining a network, via a 4-step handshake (server on UDP port 67, client on UDP port 68):
1. **DHCP Discover** — device broadcasts a request
2. **DHCP Offer** — [[Server]] offers an IP address
3. **DHCP Request** — device confirms it wants the offered IP
4. **DHCP ACK** — server acknowledges, completing the assignment

### Related
[[UDP]]

### Source:
[[16. Intro to LAN]]
[[17. OSI Model]]
[[13. Networking Essentials]]
