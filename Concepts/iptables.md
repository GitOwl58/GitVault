#domain/security #domain/networking

# iptables

Linux's classic firewall utility, built on the kernel's **Netfilter** framework. Replaced the older ipchains/ipfwadm tools from the Linux 2.4 kernel (2000) onward and became the de facto standard, though newer alternatives now exist (**nftables**, **UFW**, **FirewallD**). Rules are organized into **tables** (`filter`, `nat`, `mangle`, `raw`), each with built-in **chains** (e.g. `filter`'s INPUT/OUTPUT/FORWARD) that group rules by traffic type; each **rule** combines match criteria (protocol, port, IP...) with a **target** (ACCEPT, DROP, REJECT, LOG, SNAT/DNAT, MASQUERADE, REDIRECT, MARK). Example: `sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT` allows inbound SSH.

### Related
[[Firewall]]

### Source:
[[26. Firewall Setup]]
