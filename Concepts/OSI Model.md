#domain/networking

# OSI Model (Open Systems Interconnection)

A 7-layer framework dictating how networked devices send, receive, and interpret data. Data travels through every layer; information is added at each step (**encapsulation**).

| Layer | Name | Key job                                             |
| ----- | ------------ | --------------------------------------------------- |
| 7 | Application | User-facing protocols, DNS, [[GUI]]                 |
| 6 | Presentation | Translation/standardisation, encryption ([[HTTP]]S) |
| 5 | Session | Creates/maintains a connection (session)            |
| 4 | Transport | [[TCP]] (reliable) vs [[UDP]] (fast, no guarantee)  |
| 3 | Network | [[Routing]] via [[IP address]]                      |
| 2 | Data Link | Physical addressing via [[MAC address]]             |
| 1 | Physical | Electrical signals, hardware, [[Binary]]            |
### Related
[[Networking]]  [[MAC address]]  [[IP address]]  [[HTTP]]  [[Packet]]  [[Frame]]  [[Encapsulation]]  [[Decapsulation]]  [[DNS]]  [[UDP]]  [[TCP]]  [[Switch]]  [[Routing]]  [[Port forwarding]]  [[Binary]]  [[Firewall]]
### Source:
[[17. OSI Model]]
[[18. Packets and Frames]]
[[19. Extending your network]]
[[12. Networking Concepts]]
[[16. Wireshark The Basics]]
