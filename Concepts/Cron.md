#domain/os

# Cron

A Linux task scheduler: a daemon reads a `crontab` file of scheduled jobs, each line five time fields (minute 0-59, hour 0-23, day-of-month 1-31, month 1-12, day-of-week 0-7) followed by the command to run, e.g. `0 */6 * * * /path/to/script.sh` runs every 6th hour. The alternative on modern distros is a **[[systemd]]** timer + service pair, which needs two unit files instead of one crontab line but integrates with systemd's own logging/dependency management.

### Related
[[Cron Cheatsheet]]  [[systemd]] [[Rsync]]

### Source:
[[17. Task Scheduling]]
[[20. Backup and Restore]]
