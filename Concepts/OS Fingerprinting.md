#domain/pentesting #domain/networking

# OS Fingerprinting

Inferring a target's operating system from how it responds on the network (TCP/IP stack quirks, response timing/behaviour), rather than from anything it explicitly announces. [[Nmap]]'s `-O` flag does this: results are an educated guess, not a certainty, e.g. reporting a range like "Linux 4.X\|5.X" rather than an exact version. Often paired with service/version detection (`-sV`) or bundled together via `-A`.

### Related
[[Nmap]] [[Port Scan]]

### Source:
[[18. Nmap The Basics]]
