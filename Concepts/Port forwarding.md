#type/concept #domain/networking 

A technique that redirects network traffic arriving on a specific port of a public address to a specific machine and port inside a private network.

Useful because private addresses aren't directly reachable from outside — port forwarding acts as a "bridge" configured on the [[Router]], letting an internal service (web server, game server, SSH access...) become reachable from the Internet despite NAT.

Operates at Layer 3 and 4 of the OSI Model, using IP address and port number to redirect a private IP and internal port.

### Related:
[[Router]]  [[IP address]]  [[TCP]]  [[UDP]]  [[Firewall]]  [[Networking]]  [[OSI Model]]  [[Ports|Port]]

### Sources :
[[16. Intro to LAN]]
[[19. Extending your network]]