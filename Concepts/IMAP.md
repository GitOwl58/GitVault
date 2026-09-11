#domain/networking

# IMAP (Internet Message Access Protocol)

Keeps mail on the server and synchronizes read/moved/deleted state across multiple clients — the fit for checking one mailbox from several devices, unlike [[POP3]]. TCP port 143 by default. Key commands: `LOGIN`, `SELECT <mailbox>`, `FETCH <n> <data item>`, `MOVE`/`COPY`, `LOGOUT`.

Over [[TLS]]: **IMAPS**, port 993.

### Related
[[SMTP]] [[POP3]] [[Ports]] [[TLS]]

### Source:
[[14. Networking Core Protocols]]
[[15. Networking Secure Protocols]]
