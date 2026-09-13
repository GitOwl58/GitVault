#domain/networking

# NAT (Network Address Translation)

Lets multiple devices on a private network share one public [[IP address]] to reach the Internet: a router rewrites the source *IP and port* of outgoing packets to its own public IP and a chosen port (and back again for replies), keeping a translation table to map each reply to the right internal device/port. What lets a device on a private range actually get out to the Internet despite not being publicly routable.

### Related
[[IP address]]
[[Subnetting]]
[[Router]]

### Source:
[[12. Networking Concepts]]
[[13. Networking Essentials]]
