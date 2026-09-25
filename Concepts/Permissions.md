#domain/os #domain/security
# Permissions

Access control rules set on files and folders defining what users or groups can do.

On **Windows (NTFS)**: six levels, Read, Write, Read & Execute, List Folder Contents, Modify, Full Control, viewable via right-click → Properties → Security tab.

On **Linux**, each file/directory has an owning user and group, with separate **r**ead/**w**rite/e**x**ecute bits for owner, group, and others (`ls -l` shows this as e.g. `-rwxr-xr--`). `chmod` changes them, either symbolically (`chmod a+r file`, group refs `u`/`g`/`o`/`a`) or via octal notation (`r=4 w=2 x=1` summed per owner/group/other, e.g. `chmod 754`). `chown user:group file` changes ownership. Two special bits: **SUID/SGID** (shown as `s` in place of `x`) run a program with the file owner's/group's rights rather than the invoking user's, a common privilege-escalation vector if misconfigured; the **sticky bit** (`t`/`T` on a directory) stops non-owners deleting or renaming files inside it even with write access, used on shared directories like `/tmp`.

### Related
[[Chmod Cheatsheet]]  [[NTFS]]  [[File System]]  [[CIA Triad]] [[sudo]]
### Source:
[[13. Permission Management]]
