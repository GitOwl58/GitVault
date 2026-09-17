#domain/software

# Bitwise Operations

Operations that act directly on the individual bits of a **[[Binary]]** value rather than on it as a whole number. Three basic ones: **AND** (`&`, returns 1 only if both bits are 1), **OR** (`|`, returns 1 if either bit is 1), **NOT** (`!`, flips a single bit). Used to test or isolate specific bits within a byte, such as checking whether one particular flag bit is set without caring about the others.

Tools like [[Tcpdump]] use this to filter on raw header bytes (`proto[expr:size]` syntax) and, more practically, to match **[[TCP Flags]]**: `tcp[tcpflags] & tcp-syn != 0` uses AND to check whether the SYN bit is set, regardless of what else is set alongside it.

### Related
[[Binary]] [[Tcpdump]] [[TCP Flags]]

### Source:
[[17. Tcpdump The Basics]]
