#domain/homelab

# UPS

**Uninterruptible Power Supply**, a battery-backed device that sits between the wall outlet and the equipment plugged into it, keeping everything running through a brief power outage and giving enough time to shut down cleanly during a longer one. For a homelab, the point usually isn't riding out hours of downtime, it's avoiding a hard, unclean power loss to a server or NAS mid-write, which is how filesystems get corrupted and drives get damaged.

### Sizing, roughly
A small 1U rackmount or tower UPS in the 500VA/300W class is enough for a modest single-host homelab, giving somewhere around 20-30+ minutes of runtime at half load, plenty for either riding out a short blip or triggering an automatic clean shutdown. Most UPS units support a USB/network connection to the server so software (NUT, Proxmox's own integration, or the NAS OS's built-in support) can trigger that shutdown automatically once battery runs low, without anyone needing to be home.

### The catch
UPS batteries degrade and typically need replacing every 3-5 years, a detail that's easy to forget until the UPS fails to actually hold a charge during an outage. It's worth keeping the protected load light (the server/NAS/router, not the whole rack) rather than trying to stretch a small UPS across everything.

### Related
[[Homelab Physical Setup]] [[Rack Unit]] [[Homelab Common Mistakes]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
