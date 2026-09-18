#domain/pentesting #domain/networking

# Nmap Timing Templates

Six numbered speed presets in [[Nmap]] (`-T0` to `-T5`): paranoid, sneaky, polite, normal (default), aggressive, insane. Each controls how much delay Nmap inserts between probes, trading speed against stealth, a fast scan is much easier for an **[[IDS]]** or other defenses to notice than a slow, spread-out one. The difference is dramatic in practice: the same 100-port scan can take under a second at the fast end or hours at the slow end.

Finer control beyond the presets: `--min-parallelism`/`--max-parallelism` bound how many probes run simultaneously per host group (Nmap normally adjusts this automatically based on network reliability); `--min-rate`/`--max-rate` bound the packets-per-second rate for the whole scan, not per host; `--host-timeout` caps how long Nmap waits on one slow host before moving on.

### Related
[[Nmap]] [[Port Scan]] [[IDS]]

### Source:
[[18. Nmap The Basics]]
