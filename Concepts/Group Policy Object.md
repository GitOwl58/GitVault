#domain/os #domain/security

# Group Policy Object (GPO)

A collection of settings managed through Group Policy Management and applied to an [[Organizational Unit]] — a GPO affects the OU it's linked to and every sub-OU beneath it. Can target Computer Configuration, User Configuration, or both (e.g. restricting Control Panel access, or locking a screen after a period of inactivity).

GPOs are distributed to domain machines via **SYSVOL**, a network share that by default points to `C:\Windows\SYSVOL\sysvol\` on each [[Domain Controller]]; `gpupdate /force` forces an immediate sync.

### Related
[[Domain Controller]] [[Active directory]] [[Organizational Unit]]
### Source:
[[08. Active Directory Basics]]
