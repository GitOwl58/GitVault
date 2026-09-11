
#domain/networking

# SSH (Secure Shell)

Protocol for securely logging into systems via a text-based interface, port 22 — replaced the cleartext [[Telnet]]. Uses a private key + public certificate model (same principle VPNs borrow from). Supports password, public-key, and two-factor authentication; warns of unrecognised server keys (anti-MITM); and can tunnel other protocols through it (VPN-like) or forward a remote GUI app over the network (X11 forwarding, `ssh host -X`). [[SFTP]] rides on the same protocol suite and port.

### Related:
[[RDP]] [[FTP]] [[SFTP]] [[Networking]] [[Ports|Port]] [[Port forwarding]] [[Telnet]] [[TLS]]
### Source:
[[7. Linux CLI Basics]] 
[[18. Packets and Frames]]
[[19. Extending your network]]
[[3. Linux Fundamentals Part.2]]
[[4. Linux Fundamentals Part.3]]
[[15. Networking Secure Protocols]]
