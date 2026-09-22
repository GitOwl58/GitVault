#domain/homelab

# Homelab Physical Setup

Where and how the hardware physically lives matters more than it seems, temperature, noise, cable runs, and foot traffic all affect what's practical.

### Location tradeoffs
- **Home office**: close to your desk, fewer cable runs, but you need to have one to begin with...
- **Living room**: usually cool, lots of space, but exposed to foot traffic damage risk, someone touching/unplugging to charge a phone (yes).
- **Closet**: stealthy and accessible, but poor ventilation.
- **Basement**: cooler temps naturally, but high humidity, flooding risk for many and possible insect issues.
- **Garage**: keeps noise out of the house entirely, but dust, temperature swings, and longer cable runs (Holes drilled, etc...) Usually only worth for people running whole servers racks.

Pick the coolest realistic spot, avoid direct sunlight, and leave room for future expansion. Sketching a network diagram first before running cable saves a lot of pain, especially through concrete or unusually thick interior walls, like any hobby take things slow at the beginning, as hard as it can be when you are genuinely excited about something new/ something that is in your mind all the time.

---
### Rack vs cabinet
A **rack** is an open frame (some or all sides open); a **cabinet** is enclosed with doors/removable panels. Network gear (routers, switches, patch panels) is generally shallower and produces less heat than server gear, so network racks/cabinets are often shallower than server ones.

Choose based on:
- Heavy servers → extra stability of a cabinet or 4-sided rack.
- Frequent access to sides/rear → open rack or cabinet with removable sides.
- Extra heat output → enclosed cabinet needs more attention to airflow.
- Dusty environment → a cabinet keeps dust out better.
- Shared living space with guests → an enclosed, lockable cabinet looks tidier and keeps hands off of it.
- Security/restricted access needed → enclosed cabinets often have lock-and-key.

**Rack units**: 1U = 44.45mm, the standard measure for both frame height and equipment height. A full-size rack is 42U; home setups are commonly small wall-mount units (6U-12U is a good starting range).

---
### Power
A **[[UPS]]** (Uninterruptible Power Supply) buys time to shut down cleanly (or fail over to a generator) during an outage. A small 1U rackmount or tower UPS (roughly 500VA/300W class) is enough for a modest homelab, typically €90-160 in the EU for a reputable brand (APC, Eaton), no need to pay for hours of runtime, just enough for a clean shutdown or failover, typically 20-30+ minutes at half load for a small setup. UPS batteries are a common disappointment relative to cost and usually need replacing every 3-5 years, so it's worth keeping the load light and picking only the most essential devices to protect rather than the whole rack.

A rack-mount power strip that plugs directly into the UPS makes turning individual devices on/off easy. Outlet savers help make full use of available sockets, and blanking panels (covering unused rack space) improve airflow.

### Cooling
Equipment kept in an air-conditioned, low-dust room may not need active cooling fans at all, passive ventilation (vented shelves, blanking panels) can be enough. If active cooling is needed, rack-mount fan units work, but budget for a realistic 2-3 year lifespan before fans start failing from dust buildup, and factor in whether the unit is easy to service (some have fans hot-glued to the board, making replacement annoying).

### Cabling
16-port patch panels are a common, sufficient size for a home setup, going 24-port only matters if you expect to grow past that. **CAT6** is plenty for gigabit home connections, there's no need for CAT6a/CAT7 unless the ISP plan and internal LAN traffic actually justify it, and going to shielded cable/connectors is only worth it if the patch panel and jacks all support it too, otherwise it's wasted money. Budget slightly more cable length than the measured distance, real runs are almost always a bit longer than expected once routing around obstacles.

### Related ///Module is not finished, many deadlinks linking to contents in a draft folder///
[[Homelab Setup]] [[Homelab Hardware Tiers]] [[Router]] [[Switch]] [[UPS]] [[Rack Unit]]

### Source:
Synthesized from external homelab guides and my homelab setup.
