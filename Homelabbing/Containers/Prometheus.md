#domain/homelab

# Prometheus

A time-series metrics collector: it periodically scrapes numeric metrics (CPU load, memory, disk I/O, request counts, whatever an exporter exposes) from configured targets and stores them, building a history you can query and alert on. On its own it's just data collection and a basic query language (PromQL), the dashboards usually come from **[[Grafana]]** on top.

**Node Exporter** is the companion service that exposes host-level metrics (CPU, RAM, disk, network) for Prometheus to scrape, install it on every host you want visibility into.

### Related
[[Monitoring]] [[Grafana]] [[Homelab Backups and Maintenance]]

### Source:
Synthesized from external homelab guides, not a course lesson, drafted for review before adding to the vault.
