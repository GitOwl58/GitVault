#domain/homelab

# Homelab Hardware Tiers

What to actually buy depends entirely on budget, living situation (apartment vs house with a basement), and how far you already know you want to go. Four tiers cover almost everyone, from "just learning" to "small business grade." Prices below are rough EU street prices (VAT included where typical) as of late 2026, expect variation by country and retailer.

### Tier 1: Just learn the basics (€0-120)
An old laptop already collecting dust, or a Raspberry Pi 5. Note that Pi 5 prices have climbed noticeably through 2026 due to a global DRAM/memory shortage pushing board prices up across the board, an 8GB Pi 5 now runs roughly €190-215 from official EU resellers, well above its original launch price. If starting from zero and price-sensitive, an old laptop or a cheap used mini PC (see Tier 2) can now actually beat a brand-new Pi 5 on price. Install Ubuntu Server or Debian, put **[[Docker]]** on top. Won't run 20 containers, but enough for **[[Pi-hole]]**, a small media server, and a few extras. Idle draw: 3-5W, a few euros a year to run.

Best for: apartment dwellers with zero spare space, students, anyone unsure they'll stick with the hobby.

### Tier 2: Mini PCs (€130-350)
Beelink, Intel NUC, or Minisforum mini PCs. The "quiet homelab" : N100-class boxes (Beelink EQ12 Pro/S12 Pro-tier) run roughly €260 with 16GB RAM, idle at around 7W, and are dead silent. A step up, Ryzen-based boxes like the Beelink EQR6 (~€380) or Minisforum UM790 Pro (~€700) trade more idle power (12-22W) for real transcoding and multi-VM headroom. 16GB RAM + a small NVMe SSD runs 10-15 containers comfortably, but prices out of our budget in the mini PC category.

Best for: apartments, shared living spaces, anyone who values quiet over raw power.

### Tier 3: Used office PCs (€80-300)
Dell OptiPlex, HP EliteDesk, Lenovo ThinkCentre. Businesses cycle these out by the thousands every 3-5 years, so they show up on eBay, Backmarket (not necessarily recommended), Rebuy, and local refurbishers for not much money. An OptiPlex 7040/7060 or ThinkCentre M920 with an i5, 16-32GB RAM, and an SSD handles pretty much anything a beginner throws at it. Idle draw: 40-80W.

Best for: the best balance of price, performance, and upgradeability, the recommended starting point for most people if confortable buying second hand, browsing Ebay etc...

### Tier 4: Used enterprise servers (€60-1000+)
Dell PowerEdge, HP ProLiant, Lenovo ThinkServer. Xeon CPUs, tons of RAM slots, hardware **[[RAID]]** controllers, built to run 24/7 in a server closet so they're genuinely tanks. Barebones older-generation units (R210/R320/R630-class) can be found for €60-300 without RAM/CPU, while a fully configured R730/R640-class server with dual Xeons and 32-64GB RAM (DDR4 of course) lands more like €600-1200+ from EU server resellers. Downsides: loud (small high-RPM fans), power-hungry (100-200W+ idle on older models), heavy. Not a good starting point unless there's a basement, garage, or attic to put it in.

Best for: people with dedicated space who already know they want to go deep into virtualization and clustering, already strong knowledge base of Homelabbing.

---
### Power cost reference (EU average electricity price)
The EU household average sits around **€0.29/kWh** (H2 2025 Eurostat figures), but the spread across the continent is large: roughly €0.09-0.15/kWh in cheaper markets (Hungary, Bulgaria, much of the Balkans) up to €0.40-0.51/kWh in the most expensive (Ireland, Germany, Belgium). Use your own rate from a recent bill for anything more precise, the table below uses the EU average.

| Hardware | Idle Wattage | Monthly Cost (@ €0.29/kWh) | Annual Cost |
|---|---|---|---|
| Raspberry Pi 5 | 3-5W | ~€0.60 | ~€7 |
| Mini PC, N100-class (Beelink/NUC) | 7-10W | ~€1.50-2 | ~€18-25 |
| Mini PC, Ryzen-class (transcoding) | 12-22W | ~€2.50-4.50 | ~€30-55 |
| Used office PC (OptiPlex/ThinkCentre) | 40-80W | ~€8-17 | ~€100-200 |
| Used enterprise server (Xeon E3 class) | ~80W | ~€17 | ~€200 |
| Enterprise rack server (R730 etc.) | 100-200W | ~€21-42 | ~€250-500 |
| Two enterprise servers (a mature multi-host setup) | 250-400W | ~€53-85 | ~€630-1000 |

Rule of thumb: idle wattage × 0.0288 × 24 × 30 ≈ rough monthly cost at the EU average rate, halve it in cheap markets, roughly double it in expensive ones.

---
### What to look for in used hardware
- **CPU**: any Intel i5/i7 from the last 8-10 years, or a Xeon E3/E5, is more than enough to start.
- **RAM**: 16GB minimum, 32GB is the real sweet spot, RAM is usually the first thing you run out of, not CPU, considering the prices in 2026 DDR4 is the main format cited in this folder, as prices would double with recent DDR5 setups...
- **Storage**: matters less if a **[[NAS]]** handles bulk data, a single SSD for the OS/hypervisor is fine on the compute box itself.

### Where to buy used
In Europe: eBay.de/eBay.fr/eBay.it (best for hunting a specific model across the whole continent), Rebuy (graded, warrantied refurbished stock, slightly pricier but lower risk), local classifieds (Marktplaats, Leboncoin, Vinted for smaller gear, Kleinanzeigen), dedicated EU server resellers (for enterprise gear specifically) and local e-waste/business-liquidation recyclers.

### A real example
One build: a used Lenovo ThinkServer for around €150, Xeon E3-1226 v3 (4 cores), 32GB RAM, 2TB HDD. Enough for 15-20 containers comfortably, and having run 24/7 in an office for years before resale, it's built for exactly this kind of continuous duty.

### Related
[[Homelab Setup]] [[Homelab Physical Setup]] [[Proxmox]] [[Docker]] [[NAS]] [[RAID]] [[Pi-hole]]

### Source:
Compiled data from external homelab guides, will be updated, checked for errors regularly...
