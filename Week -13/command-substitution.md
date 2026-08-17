# Command Substitution

## 📌 Overview

Command substitution allows the output of a command to be used as the value of a variable.

The preferred syntax is:

```bash
$(command)
```

Command substitution is useful when a script needs to capture information produced by another command.

---

# Example 1 – Get the Current Date

### Command

```bash
CURRENT_DATE=$(date +"%Y-%m-%d")
echo "Today's date is: $CURRENT_DATE"
```

### Explanation

```bash
$(date +"%Y-%m-%d")
```

runs the `date` command and captures its output.

The output is stored in the `CURRENT_DATE` variable.

### Example Output

```text
Today's date is: 2026-08-17
```

The actual date depends on the system when the script is executed.

---

# Example 2 – Store Directory Listing

### Command

```bash
FILES_IN_DIR=$(ls)

echo "Files in the current directory:"
echo "$FILES_IN_DIR"
```

### Explanation

```bash
$(ls)
```

runs the `ls` command and captures its output.

The output is stored in the `FILES_IN_DIR` variable.

### Example Output

```text
Files in the current directory:
variables.sh
```

The actual files displayed depend on the current directory.

---

# Example 3 – Get System Uptime

### Command

```bash
UPTIME=$(uptime -p)

echo "System uptime: $UPTIME"
```

### Explanation

```bash
$(uptime -p)
```

runs `uptime -p` and stores its output in the `UPTIME` variable.

### Example Output

```text
System uptime: up 2 hours, 15 minutes
```

The actual output depends on the system uptime.

---

# Example 4 – Multiple Command Substitutions

### Script

```bash
#!/bin/bash

CURRENT_DATE=$(date +"%Y-%m-%d")
FILES_IN_DIR=$(ls)
UPTIME=$(uptime -p)

echo "Today's date is: $CURRENT_DATE"
echo "Files in the current directory:"
echo "$FILES_IN_DIR"
echo "System uptime: $UPTIME"
```

### Example Output

```text
Today's date is: 2026-08-17
Files in the current directory:
variables.sh
System uptime: up 2 hours, 15 minutes
```

The actual values depend on the system.

---

# Command Substitution Syntax

### Preferred Syntax

```bash
$(command)
```

### Older Syntax

```bash
`command`
```

The `$()` syntax is generally easier to read and can be nested more easily.

---

# Practical Example – Create a Date-Based Backup Name

Command substitution can be used when a script needs the current date to create a dynamic filename.

```bash
#!/bin/bash

DATE=$(date +"%Y-%m-%d")
BACKUP_NAME="backup-$DATE.tar"

echo "Creating backup: $BACKUP_NAME"
```

### Output

```text
Creating backup: backup-2026-08-17.tar
```

### Why This Is Useful

The date is generated automatically instead of being manually entered.

This can be useful for:

- Backup files
- Log files
- Reports
- Date-based directories
- Temporary filenames

---

# Practical Applications

- Getting the current date
- Capturing command output
- Storing system information
- Creating dynamic filenames
- Using command output inside scripts
- Automating Linux tasks

---

# Key Learnings

- Command substitution captures command output.
- `$()` is used for command substitution.
- The captured output can be stored in a variable.
- Commands such as `date`, `ls`, and `uptime` can be used with command substitution.
- Command substitution makes shell scripts more dynamic.
