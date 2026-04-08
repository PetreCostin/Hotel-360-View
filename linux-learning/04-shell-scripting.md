# Shell Scripting

## What is a Shell Script?

A shell script is a plain-text file containing a sequence of shell commands. The shell reads the file and executes the commands in order, enabling automation of repetitive tasks.

## Creating Your First Script

```bash
#!/bin/bash
# hello.sh — print a greeting

echo "Hello, World!"
```

Save the file, make it executable, and run it:

```bash
chmod +x hello.sh
./hello.sh
```

The first line (`#!/bin/bash`) is called the **shebang** and tells the OS which interpreter to use.

## Variables

```bash
#!/bin/bash
name="Alice"
echo "Hello, $name"

# Command substitution
today=$(date +%F)
echo "Today is $today"

# Read user input
read -p "Enter your name: " username
echo "Welcome, $username"
```

## Conditional Statements

```bash
#!/bin/bash
x=10

if [ $x -gt 5 ]; then
    echo "$x is greater than 5"
elif [ $x -eq 5 ]; then
    echo "$x equals 5"
else
    echo "$x is less than 5"
fi
```

Common comparison operators:

| Operator | Meaning |
|----------|---------|
| `-eq` | Equal |
| `-ne` | Not equal |
| `-lt` | Less than |
| `-le` | Less than or equal |
| `-gt` | Greater than |
| `-ge` | Greater than or equal |
| `-z` | String is empty |
| `-n` | String is not empty |
| `-f` | Path is a regular file |
| `-d` | Path is a directory |

## Loops

**For loop**:
```bash
for fruit in apple banana cherry; do
    echo "Fruit: $fruit"
done
```

**While loop**:
```bash
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    count=$((count + 1))
done
```

**Iterate over files**:
```bash
for file in *.txt; do
    echo "Processing $file"
done
```

## Functions

```bash
#!/bin/bash

greet() {
    local name="$1"   # First argument
    echo "Hello, $name!"
}

greet "Bob"
greet "Carol"
```

## Exit Codes

Every command returns an exit code: `0` means success, non-zero means failure.

```bash
ls /nonexistent
echo "Exit code: $?"   # Prints non-zero

# Exit with a specific code
exit 1
```

## Practical Example: Backup Script

```bash
#!/bin/bash
# backup.sh — back up a directory with a timestamp

SOURCE="$1"
DEST="$HOME/backups"
TIMESTAMP=$(date +%Y%m%d_%H%M%S)

if [ -z "$SOURCE" ]; then
    echo "Usage: $0 <source-directory>"
    exit 1
fi

if [ ! -d "$SOURCE" ]; then
    echo "Error: '$SOURCE' is not a directory"
    exit 1
fi

mkdir -p "$DEST"
cp -r "$SOURCE" "$DEST/${TIMESTAMP}_$(basename "$SOURCE")"
echo "Backup created at $DEST/${TIMESTAMP}_$(basename "$SOURCE")"
```

Run it:
```bash
chmod +x backup.sh
./backup.sh ~/documents
```
