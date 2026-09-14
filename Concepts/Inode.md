#domain/os

# Inode

A metadata record the Linux filesystem keeps for every file and directory: permissions, size, type, owner, and more: effectively a database entry the OS queries to manage files, separate from the file's actual data blocks. `ls -il` shows each entry's inode number alongside its normal listing. Regular files, directories, and symbolic links are the three ways content is represented in this structure.

### Related
[[File System]] [[Permissions]]

### Source:
[[21. File System Management]]
