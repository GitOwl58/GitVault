#type/concept #domain/os #domain/security

# Volume Shadow Copy Service (VSS)

A Windows service that creates a consistent point-in-time snapshot ("shadow copy") of data being backed up, stored in the `System Volume Information` folder of each protected drive. When System Protection is enabled, it lets you create/restore to a restore point, configure restore settings, or delete restore points.

Security relevance: ransomware often specifically looks for and deletes shadow copies to block easy recovery — an offline/off-site backup still matters even with VSS enabled.

### Related
[[Ransomware]] [[Windows]] [[Malware]]
### Source:
[[7. Windows Fundamentals Part.3]]
