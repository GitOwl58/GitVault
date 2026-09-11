#domain/networking

# Three-way handshake

How [[TCP]] establishes a connection before sending data:
1. **SYN** — client sends its initial sequence number (ISN) to synchronise
2. **SYN-ACK** — server replies with its own ISN and acknowledges the client's
3. **ACK** — client acknowledges the server's ISN; connection is now open

Each octet gets a sequence number so the receiver can detect lost/duplicated data; the ACK number always echoes the last sequence number received. [[UDP]] skips this entirely — no handshake, no ordering guarantee.

### Related
[[TCP]]
[[UDP]]
[[Encapsulation]]

### Source:
[[18. Packets and Frames]]
[[12. Networking Concepts]]
