#type/Setup_guide
# Proton Drive on Linux CachyOS / Hyprland with rclone

## What this will do:

Proton Drive mounted at `~/ProtonDrive` as a normal folder, mounted automatically at every login, using rclone's `protondrive` backend.

It's a live view of your drive, not a synced copy: anything you do in the folder happens on Proton. Deletes end up in Proton's trash and a version history is kept when overwritting, so local mistakes can still be fixed from the app.

## 1. Install dependencies

You need `rclone` (1.64.0 or newer...) and `fuse3` for mounting. `unzip` is only needed for rclone's install script, not with pacman.

```bash
sudo pacman -S rclone fuse3
rclone version
which rclone fusermount3
```

Note the paths `which` prints (normally `/usr/bin/rclone` and `/usr/bin/fusermount3`). 
The systemd unit later needs them. 
On Arch, fuse3 ships `fusermount3`, and plain `fusermount` may not exist.

## 2. Configure the proton remote

There's no browser login for Proton. The wizard asks for your username and password in the terminal.

```bash
rclone config
```

1. `n` for a new remote, name it `proton`.
2. Pick `protondrive` (49) as the storage type.
3. Enter your Proton username and password.
4. Leave the 2FA field empty, keep the other advanced options at their defaults, then save and quit.

Then log in once quickly with a fresh 2FA code from your authenticator app:

```bash
rclone lsd proton: --protondrive-2fa=XXXXXX
```

If it lists your top-level folders, you're in. rclone now caches session tokens in its config (`client_uid`, `client_access_token`, `client_refresh_token`, `client_salted_key_pass`) and won't ask for 2FA again until Proton kills the session.

Don't store a 2FA code in the config or in a script, it dies after 30 seconds, and when the session expires rclone will send that stale code and fail with error 8002.

Your 2FA must be from an authenticator app, a security key on its own isn't supported by rclone.

## 3. Test-mount manually

```bash
mkdir -p ~/ProtonDrive
rclone mount proton: ~/ProtonDrive --vfs-cache-mode writes --daemon
ls ~/ProtonDrive
```

`--vfs-cache-mode writes` is basically required. Proton's backend cannot do partial writes, so without it editors and apps that seek or rewrite files (Obsidian, nvim, LibreOffice) throw errors. Use `full` instead if you also want reads cached on disk, for example for media.

`--daemon` backgrounds the mount. Drop it and add `-v` if you want to watch the logs while testing.

Unmount before moving on, or the service in step 4 will fail on a busy mountpoint:

```bash
fusermount3 -u ~/ProtonDrive
```

## 4. Auto-mount at login (systemd user service)

`~/.config/systemd/user/` doesn't exist on a fresh install. It's where your own user units go, so create it:

```bash
mkdir -p ~/.config/systemd/user
vim ~/.config/systemd/user/rclone-proton.service
```

You can use vim, nano, whatever text editor you prefer.

```ini
[Unit]
Description=rclone Proton Drive mount
After=network-online.target

[Service]
Type=notify
ExecStartPre=/usr/bin/mkdir -p %h/ProtonDrive
ExecStart=/usr/bin/rclone mount proton: %h/ProtonDrive --vfs-cache-mode writes --dir-cache-time 30s
ExecStop=/usr/bin/fusermount3 -uz %h/ProtonDrive
Restart=on-failure
RestartSec=15

[Install]
WantedBy=default.target
```

In case you do not know:

- `%h` is your home directory.
- `Type=notify` works because rclone tells systemd when the mount is actually ready. No `--daemon` here, since systemd handles background.
- `--dir-cache-time 30s` makes changes made on the web or phone show up locally within about 30s. The default is 5 minutes,you do not have to change this setting.
- `-uz` does a lazy unmount, so logout or shutdown won't hang on an open file.
- `Restart=on-failure` plus `RestartSec=15` retries until the network is up, every 15s.

Enable and start it:

```bash
systemctl --user daemon-reload
systemctl --user enable --now rclone-proton
systemctl --user status rclone-proton
```

You want `active (running)`. It starts at login rather than boot, since it's a user service. With uwsm, the Hyprland session runs on systemd, so `default.target` picks it up without any `exec-once`.

## 5. How the mount behaves

Edits sync up a few seconds after you close the file. rclone writes to a local cache (`~/.cache/rclone/vfs/`) first, then uploads after a 5s delay (`--vfs-write-back`).

- **Deletes go to Proton's trash.** Restore from the web app. (Tested: `rm` in the mount puts the file in the web trash.)
- **Overwrites keep version history.** Old versions show up under the file's version history in the web app. (Tested.)
- **Don't unmount or shut down mid-upload.** Let big copies finish first.
- **No offline access.** If the mount or the network is down, the folder is empty.
- **Web-side changes lag** by up to `--dir-cache-time` (30s with the unit above). To force a refresh now: `systemctl --user kill -s HUP rclone-proton`.

Trash and versions protect against local mistakes, not against losing access to the account. For anything important, keep a second copy elsewhere, for example with an occasional `rclone sync proton: /path/to/local/backup`.

## Cheat sheet

| Task | Command |
| --- | --- |
| Status | `systemctl --user status rclone-proton` |
| Logs | `journalctl --user -u rclone-proton -e` |
| Restart | `systemctl --user restart rclone-proton` |
| Stop / unmount | `systemctl --user stop rclone-proton` |
| Refresh listings now | `systemctl --user kill -s HUP rclone-proton` |
| Re-login (2FA) | `rclone lsd proton: --protondrive-2fa=CODE` |
| Disable auto-mount | `systemctl --user disable --now rclone-proton` |
