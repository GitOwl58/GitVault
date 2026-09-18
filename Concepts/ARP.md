#domain/networking

# ARP (Address Resolution Protocol)

Allows a device to associate its [[MAC address]] with an [[IP address]] on the network. Each device keeps a CACHE (log) of other devices' MAC addresses.

- **ARP request**: broadcast asking "what is the MAC address owning this IP?"
- **ARP reply**: only the owning device replies; requester stores it in its ARP cache.

Debated whether it belongs to Layer 2 (deals in MAC addresses) or Layer 3 (supports IP operations); it bridges the two.

Source: 
[[16. Intro to LAN]]
[[17. OSI Model]]
[[13. Networking Essentials]]
[[18. Nmap The Basics]]

