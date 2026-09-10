#type/concept #domain/networking

# ARP (Address Resolution Protocol)

Allows a device to associate its [[MAC address]] with an [[IP address]] on the network. Each device keeps a CACHE (log) of other devices' MAC addresses.

- **ARP request**: broadcast asking "what is the MAC address owning this IP?"
- **ARP reply**: only the owning device replies; requester stores it in its ARP cache.

Source: 
[[16. Intro to LAN]]
[[17. OSI Model]]

