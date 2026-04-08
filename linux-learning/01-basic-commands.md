# Basic Linux Commands

## Navigation

| Command | Description | Example |
|---------|-------------|---------|
| `pwd` | Print working directory | `pwd` |
| `ls` | List directory contents | `ls -la` |
| `cd` | Change directory | `cd /home/user` |
| `cd ..` | Go up one level | `cd ..` |
| `cd ~` | Go to home directory | `cd ~` |

## File and Directory Management

| Command | Description | Example |
|---------|-------------|---------|
| `touch` | Create an empty file | `touch file.txt` |
| `mkdir` | Create a directory | `mkdir my-folder` |
| `mkdir -p` | Create nested directories | `mkdir -p a/b/c` |
| `cp` | Copy files or directories | `cp file.txt backup.txt` |
| `mv` | Move or rename | `mv old.txt new.txt` |
| `rm` | Remove a file | `rm file.txt` |
| `rm -r` | Remove a directory recursively | `rm -r my-folder` |

## Viewing File Contents

| Command | Description | Example |
|---------|-------------|---------|
| `cat` | Print entire file | `cat file.txt` |
| `less` | Scroll through a file | `less file.txt` |
| `head` | Show first 10 lines | `head file.txt` |
| `tail` | Show last 10 lines | `tail file.txt` |
| `tail -f` | Follow a growing file | `tail -f /var/log/syslog` |

## Searching

| Command | Description | Example |
|---------|-------------|---------|
| `grep` | Search text in files | `grep "error" app.log` |
| `grep -r` | Search recursively | `grep -r "TODO" ./src` |
| `find` | Find files by name/type | `find . -name "*.txt"` |

## System Information

| Command | Description | Example |
|---------|-------------|---------|
| `uname -a` | Kernel and system info | `uname -a` |
| `df -h` | Disk usage (human-readable) | `df -h` |
| `du -sh` | Directory size | `du -sh /var/log` |
| `free -h` | Memory usage | `free -h` |
| `top` | Live process monitor | `top` |
| `ps aux` | Snapshot of processes | `ps aux` |

## Useful Shortcuts

- `Ctrl+C` — Cancel the current command
- `Ctrl+Z` — Suspend a process
- `Ctrl+D` — Exit a shell session
- `Tab` — Auto-complete commands and file names
- `↑ / ↓` — Navigate command history
