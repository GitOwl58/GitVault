#domain/homelab

# Homelab Networking Basics

A recap of core networking concepts, specifically through the lens of setting up a homelab. This note assumes no prior networking background; if the vault already has deeper notes on any of these ([[Router]], [[Switch]], [[DHCP]], [[Subnetting]], [[VLAN]], [[IP address]], [[OSI Model]]), treat this as the homelab summary/vulgarization and those as the reference.

### The core devices
A **[[Router]]** connects your home network to the internet and directs traffic between networks. A **[[Switch]]** connects devices within the same local network so they can talk to each other, most home routers have a small switch built in, but a homelab quickly outgrows the 4-5 ports on a typical ISP router. An **access point** provides Wi-Fi, sometimes built into the router, sometimes a separate device for better coverage.

### IP addressing
Think of an IP address like a house address, it identifies a specific device on a network. A **public IP** is how your whole network is seen from the internet (usually one, assigned by your ISP), a **private IP** is how devices are addressed inside your own network, and isn't directly reachable from the internet.

Private IP ranges are reserved specifically so they never collide with public internet addresses (RFC1918):

|Range|CIDR|Common use|
|---|---|---|
|10.0.0.0 – 10.255.255.255|10.0.0.0/8|Large networks|
|172.16.0.0 – 172.31.255.255|172.16.0.0/12|Medium networks|
|192.168.0.0 – 192.168.255.255|192.168.0.0/16|Home networks (most common default)|

**DHCP** (Dynamic Host Configuration Protocol) automatically assigns IP addresses to devices when they join the network, so nobody has to manually configure every device. For servers and self-hosted services, a **static IP** (or a DHCP reservation, same effect, still managed centrally) is preferred, so the address never changes and other devices/services can reliably find it.

### Subnetting, simplified
A subnet mask (like `/24`, short for `255.255.255.0`) splits an IP address into a **network ID** (which network a device belongs to ?) and a **host ID** (which specific device within that network ?). A `/24` network gives 254 usable host addresses, more than we would need... Two devices on the same subnet can talk directly, devices on different subnets need a router to pass traffic between them.

### Why segment a network ? (VLANs)
As our homelab grows, especially once something is exposed to the internet, it's worth separating traffic: a VLAN (Virtual LAN) lets one physical network behave like several isolated ones. Common use: trusted devices (laptops, phones) on one VLAN, [[IoT]] on another, and anything internet-facing (a reverse-proxied service) on a third, so that if one segment gets compromised, it can't freely reach others.

### A troubleshooting shortcut (OSI model, simplified)
When something isn't working, it helps to troubleshoot in layers, from bottom to top, rather than guessing randomly:
- Can you `ping` the device's IP? If not, the problem is likely at the **Network Layer** (routing, cabling, device is down).
- Can you ping it but the service itself doesn't respond (web page won't load, app can't connect)? The problem is more likely at the **Application Layer** (the service itself, a wrong port, a firewall rule...).

This way of questioning (can I reach it at all ? can I reach the specific service ?) resolves a large share, but not all, of troubleshooting quickly.

### Remote access, briefly
Reaching the homelab from outside the home network is its own topic (see **[[Self-Hosted Service Stack]]**), but in short: **[[WireGuard]]** run directly, is fast and fully self-hosted but needs manual key management and, usually, port forwarding on the router (Not recommended for beginners, unlinke what many beginner homelab guides will suggest, at least in my opinion...). **Tailscale** wraps WireGuard with automatic key exchange and NAT traversal (no port forwarding needed in most cases), trading a small amount of self-hosting purity for a much easier and safer setup, a common and reasonable choice for a first remote-access setup.

### Related ///Module is not finished, many deadlinks linking to contents in a draft folder///
[[Homelab Setup]] [[Router]] [[Switch]] [[DHCP]] [[Subnetting]] [[VLAN]] [[IP address]] [[OSI Model]] [[Firewall]] [[WireGuard]]

### Source:
Compiled data from external homelab guides, will be updated, checked for errors regularly...
