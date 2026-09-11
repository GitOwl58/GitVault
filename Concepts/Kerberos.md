#domain/security #domain/networking

# Kerberos

The default network authentication protocol on any recent [[Windows domain]] — ticket-based, so it never sends a password over the network. Key parts:
- **Key Distribution Center (KDC)** — issues tickets on the network.
- **Ticket Granting Ticket (TGT)** — proves the user already authenticated and lets them request further Ticket Granting Service (TGS) tickets for specific services, without re-entering credentials.
- **Session Key** — issued alongside the TGT to authenticate subsequent requests.
- **krbtgt** — the account whose password hash encrypts the TGT.
- **Service Principal Name (SPN)** — identifies the service being accessed; its Service Owner Hash encrypts the TGS ticket.

Superseded **NetNTLM** as the default, which is now kept only for legacy compatibility.

### Related
[[Domain Controller]] [[Active directory]] [[Encryption]]
### Source:
[[8. Active Directory Basics]]
