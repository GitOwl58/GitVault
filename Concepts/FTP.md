#domain/networking

File Transfer Protocol (FTP) is a protocol designed to help the efficient transfer of files between different and even non-compatible systems. It supports two modes for file transfer: binary and [[ASCII]] (text).

TCP port 21 by default; the actual data transfer happens over a separate connection. Client commands: `USER`/`PASS` to authenticate, `RETR` to download, `STOR` to upload. Many servers allow anonymous login (username `anonymous`, no password).

### Related
[[FTPS]] | [[SFTP]] | [[RDP]] | [[SMB]] | [[SSH]] | [[ASCII]] | [[Binary]]  [[Ports|Port]]  [[URL]]


### Source :
[[18. Packets and Frames]]
[[21. HTTP in detail]]
[[14. Networking Core Protocols]]
[[15. Networking Secure Protocols]]
