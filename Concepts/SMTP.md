#domain/networking

# SMTP (Simple Mail Transfer Protocol)

Governs how a mail client sends an email to a mail server, and how servers relay to each other. TCP port 25 by default. Key commands: `HELO`/`EHLO` (open session), `MAIL FROM`/`RCPT TO` (sender/recipient), `DATA` (start message body, ended by a lone `.`).

Over [[TLS]]: **SMTPS**, ports 465/587.

### Related
[[POP3]] [[IMAP]] [[Ports]] [[TLS]]

### Source:
[[14. Networking Core Protocols]]
[[15. Networking Secure Protocols]]
