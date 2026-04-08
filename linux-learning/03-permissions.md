# Linux Permissions

## Permission Model

Every file and directory has three sets of permissions for three classes of users:

| Class | Symbol | Description |
|-------|--------|-------------|
| Owner | `u` | The user who owns the file |
| Group | `g` | Members of the file's group |
| Others | `o` | Everyone else |

Each set contains three bits:

| Permission | Symbol | Octal | Effect on file | Effect on directory |
|------------|--------|-------|----------------|---------------------|
| Read | `r` | 4 | View contents | List contents |
| Write | `w` | 2 | Modify contents | Create/delete files |
| Execute | `x` | 1 | Run as a program | Enter the directory |

## Reading Permission Strings

```
-rwxr-xr--
```

| Position | Meaning |
|----------|---------|
| 1 | File type (`-` file, `d` dir, `l` link) |
| 2-4 | Owner permissions (`rwx`) |
| 5-7 | Group permissions (`r-x`) |
| 8-10 | Others permissions (`r--`) |

## Changing Permissions: `chmod`

**Symbolic mode**:
```bash
chmod u+x script.sh      # Add execute for owner
chmod g-w file.txt       # Remove write for group
chmod o=r file.txt       # Set others to read-only
chmod a+x script.sh      # Add execute for all
```

**Octal mode**:
```bash
chmod 755 script.sh      # rwxr-xr-x
chmod 644 file.txt       # rw-r--r--
chmod 600 secret.key     # rw-------
chmod 777 public.sh      # rwxrwxrwx (avoid in production)
```

## Changing Ownership: `chown` and `chgrp`

```bash
# Change owner
sudo chown alice file.txt

# Change owner and group
sudo chown alice:developers file.txt

# Change group only
sudo chgrp developers file.txt

# Apply recursively to a directory
sudo chown -R alice:developers /var/www/app
```

## Special Permissions

| Bit | Name | Effect |
|-----|------|--------|
| `s` on owner execute | SetUID | Execute as the file's owner |
| `s` on group execute | SetGID | Execute as the file's group; new files inherit group |
| `t` on others execute | Sticky Bit | Only owner can delete files (common on `/tmp`) |

```bash
chmod u+s /usr/bin/passwd   # SetUID
chmod g+s /var/shared       # SetGID on directory
chmod +t /tmp               # Sticky bit
```

## Viewing Permissions

```bash
ls -l file.txt          # Long listing
stat file.txt           # Detailed metadata
```
