#domain/networking

# POP3 (Post Office Protocol v3)

Downloads email from a server to one client, typically deleting it server-side afterward, which minimizes server storage but doesn't synchronize across devices. TCP port 110 by default. Key commands: `USER`/`PASS`, `STAT`/`LIST`, `RETR <n>`, `DELE <n>`, `QUIT`.

Over [[TLS]]: **POP3S**, port 995.

### Related
[[SMTP]] [[IMAP]] [[Ports]] [[TLS]]

### Source:
[[14. Networking Core Protocols]]
[[15. Networking Secure Protocols]]
