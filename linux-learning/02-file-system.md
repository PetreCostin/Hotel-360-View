# Linux File System

## Directory Structure

Linux uses a single hierarchical tree rooted at `/` (root). Common directories:

| Directory | Purpose |
|-----------|---------|
| `/` | Root of the entire file system |
| `/bin` | Essential user binaries (e.g., `ls`, `cp`) |
| `/sbin` | System administration binaries |
| `/etc` | System-wide configuration files |
| `/home` | User home directories (`/home/alice`) |
| `/root` | Home directory of the root user |
| `/var` | Variable data: logs, caches, spool files |
| `/tmp` | Temporary files (cleared on reboot) |
| `/usr` | User programs and data |
| `/lib` | Shared libraries needed by `/bin` and `/sbin` |
| `/dev` | Device files (disks, terminals, etc.) |
| `/proc` | Virtual filesystem exposing kernel/process info |
| `/mnt` | Temporary mount points |
| `/media` | Auto-mounted removable media |

## Absolute vs Relative Paths

- **Absolute path**: starts from `/` — e.g., `/home/alice/documents`
- **Relative path**: starts from the current directory — e.g., `documents/notes.txt`

Special symbols:
- `.` — current directory
- `..` — parent directory
- `~` — current user's home directory

## Working with Paths

```bash
# Show current directory
pwd

# List files with details
ls -lh /etc

# Navigate using an absolute path
cd /var/log

# Navigate using a relative path
cd ../cache

# Go home
cd ~
```

## Mounting and Unmounting

```bash
# List mounted file systems
mount

# Mount a device
sudo mount /dev/sdb1 /mnt/usb

# Unmount a device
sudo umount /mnt/usb

# Show disk usage
df -h
```

## Links

**Hard link** — another name for the same inode (file data):
```bash
ln original.txt hardlink.txt
```

**Symbolic (soft) link** — a pointer to another path:
```bash
ln -s /path/to/original symlink.txt
```
