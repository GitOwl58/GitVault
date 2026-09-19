#domain/homelab

# Mosquitto (MQTT)

A lightweight message broker implementing **MQTT**, a publish/subscribe messaging protocol widely used by smart home devices and IoT gadgets to send small, frequent updates (a sensor reading, a state change) without the overhead of a full HTTP request each time. A device "publishes" to a topic (e.g. `home/livingroom/temperature`), and anything subscribed to that topic (like **[[Home Assistant]]**) receives it instantly.

Mosquitto itself is just the broker, the message router in the middle, it doesn't do anything with the data on its own. It's almost always paired with Home Assistant or a similar automation hub that actually acts on the messages passing through.

### Related
[[Smart Home]] [[Home Assistant]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
