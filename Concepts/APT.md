#domain/os

# APT

The Advanced Package Tool: Debian/Ubuntu's high-level package manager, wrapping **dpkg** (which installs individual `.deb` files) with automatic dependency resolution. Pulls from repositories listed in `/etc/apt/sources.list` (or `/etc/apt/sources.list.d/*.list`), labelled stable/testing/unstable.

Common commands: `apt-cache search <term>` (search the local cache), `apt-cache show <package>` (view metadata), `apt list --installed`, `sudo apt install <package> -y`. Packages can also be installed manually with `sudo dpkg -i <file>.deb` after downloading a `.deb` directly.

### Related
[[Parrot OS]]

### Source:
[[2. Linux Distributions]]
[[15. Package Management]]
