#domain/networking

# VNC

Virtual Network Computing: Linux's most common remote-desktop protocol (based on the RFB protocol), encrypted and authenticated by design, unlike bare X11. Two server models: sharing the host's live screen, or hosting separate virtual sessions per login (terminal-server style). A VNC server listens on TCP 5900 for display 0, with further displays on 590x. Common implementations: TigerVNC, TightVNC, RealVNC, UltraVNC. Best practice is tunneling the connection over **[[SSH]]** rather than exposing it directly, since VNC's own encryption is weaker than an SSH tunnel.

### Related
[[SSH]] [[RDP]]

### Source:
[[24. Remote Desktop Protocols in Linux]]
