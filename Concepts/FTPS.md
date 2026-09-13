#domain/networking #domain/security

# FTPS (FTP Secure)

[[FTP]] wrapped in [[TLS]]: same idea as HTTPS, but for file transfer. Requires a proper TLS certificate and usually runs on port 990. Uses separate control and data connections, which makes it trickier to pass through strict firewalls. Not to be confused with [[SFTP]], which secures file transfer via SSH instead.

### Related
[[FTP]] [[SFTP]] [[TLS]] [[Certificate]] [[Ports|Port]]

### Source:
[[15. Networking Secure Protocols]]
