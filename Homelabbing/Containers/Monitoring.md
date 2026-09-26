#domain/homelab

# Monitoring

Keeping an eye on what's running matters as much as backing it up, see **[[Homelab Backups and Maintenance]]** for the fuller picture. Two rough approaches: simple uptime checks, or deep metrics and dashboards.

### Options
- **[[Uptime Kuma]]**: simple, clean "is it up" monitoring with a nice status page, the easiest starting point.
- **[[Prometheus]]** + **[[Grafana]]** (+ Node Exporter for host-level metrics): the deeper option, collects time-series metrics and builds real dashboards, more setup effort but far more visibility once running.
- **Zabbix** / **Checkmk RAW**: heavier, more "enterprise-flavored" alternatives, worth it mainly for larger or multi-host environments where Prometheus/Grafana starts to feel like too many moving parts to hand-configure.

### Related
[[Uptime Kuma]] [[Prometheus]] [[Grafana]] [[Homelab Backups and Maintenance]]
