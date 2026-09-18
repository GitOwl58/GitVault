#domain/os

# File Descriptor

The kernel's handle for an I/O connection (Windows: filehandle). Every process gets three by default: **STDIN** (FD 0, input), **STDOUT** (FD 1, output), **STDERR** (FD 2, error output). Redirection operators route these: `>` overwrites STDOUT to a file, `>>` appends, `<` feeds a file in as STDIN, `2>` redirects STDERR (e.g. `2>/dev/null` discards it), and `|` (pipe) feeds one process's STDOUT into the next process's STDIN.

### Related
[[bash]] [[grep]]

### Source:
[[10. File Descriptors and Redirections]]
[[09. Find Files and Directories]]
