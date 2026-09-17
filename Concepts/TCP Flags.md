#domain/networking

# TCP Flags

Single-bit fields in the [[TCP]] header that signal a segment's role in the connection. The **[[Three-way handshake]]** only uses two of them (SYN, ACK), but the full set includes: **SYN** (open a connection), **ACK** (acknowledge received data), **FIN** (close a connection gracefully), **RST** (abort a connection immediately), **PSH** (push buffered data to the application right away instead of waiting to fill a buffer).

Multiple flags can be set on the same segment (e.g. a SYN-ACK sets both). Tools like [[Tcpdump]] can filter on exactly which flags are set using **[[Bitwise Operations]]**, e.g. matching only SYN, or matching "SYN or ACK, whichever is set."

### Related
[[TCP]] [[Three-way handshake]] [[Tcpdump]] [[Bitwise Operations]]

### Source:
[[17. Tcpdump The Basics]]
