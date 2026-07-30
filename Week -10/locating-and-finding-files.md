# Locating and Finding Files in Linux

## `whereis`

The `whereis` command is used to locate the binary executable, source code, and manual page of a command.

### Syntax

```bash
whereis command_name
```

### Example

```bash
whereis ls
```

**Output**

```text
ls: /usr/bin/ls /usr/share/man/man1/ls.1.gz
```

### Explanation

- `/usr/bin/ls` → Location of the executable (binary) file.
- `/usr/share/man/man1/ls.1.gz` → Location of the manual page.

> **Note:** `/usr/bin` is a common directory that stores user command executables.

---

## `whereis` Options

### Find Only Binary Files

```bash
whereis -b grep
```

**Output**

```text
grep: /usr/bin/grep
```

Searches only for executable files.

---

### Find Only Manual Pages

```bash
whereis -m grep
```

Returns only the location of the manual page.

---

### Find Only Source Files

```bash
whereis -s grep
```

Returns only the source files if available.

---

# `find` Command

The `find` command is used to search for files and directories based on different criteria such as:

- Name
- Type
- Size
- Permissions
- Owner
- Modification time

---

## Searching by Name

### Syntax

```bash
find <directory> -name "filename"
```

### Example

```bash
find . -name "clue.txt"
```

### Explanation

- `find` → Search command.
- `.` → Current directory.
- `-name` → Search by exact filename.
- `"clue.txt"` → Filename to search.

---

## Searching Multiple File Types

```bash
find . -name "*.txt" -o -name "*.log"
```

### Explanation

- `*.txt` → All text files.
- `*.log` → All log files.
- `-o` → Logical OR operator.

---

## Finding Files by Type

```bash
find . -type f
```

Searches only for regular files.

### Common File Types

| Type | Description |
|------|-------------|
| `f` | Regular File |
| `d` | Directory |
| `l` | Symbolic Link |

---

## Finding Files by Size

```bash
find . -type f -size +1M
```

Finds files larger than **1 MB**.

### Size Prefix

| Prefix | Meaning |
|---------|---------|
| `+1M` | Greater than 1 MB |
| `1M` | Exactly 1 MB |
| `-1M` | Less than 1 MB |

### Size Units

| Unit | Meaning |
|------|---------|
| `c` | Bytes |
| `k` | Kilobytes |
| `M` | Megabytes |
| `G` | Gigabytes |

---

## Finding Recently Modified Files

```bash
find . -type f -mtime -1
```

### `mtime` Values

| Value | Meaning |
|-------|---------|
| `-1` | Modified within the last 24 hours |
| `1` | Modified approximately 1 day ago |
| `+1` | Modified more than 1 day ago |

---

## Executing Commands on Found Files

```bash
find . -name "*.txt" -exec cat {} \;
```

### Explanation

- `-exec` → Execute a command on each matched file.
- `cat` → Command to execute.
- `{}` → Placeholder replaced with each filename.
- `\;` → Marks the end of the command.

### Example Output

```text
The suspect was last seen wearing...
```

---

## Summary

### `whereis`

- Locate executable files.
- Locate manual pages.
- Locate source files.

### `find`

- Search by filename.
- Search multiple file types.
- Search by file type.
- Search by file size.
- Search by modification time.
- Execute commands on matching files.
