# System Monitoring and Disk Usage Commands in Linux

## 📌 Overview

Linux provides several built-in commands to monitor system performance, memory usage, running processes, and disk usage. The `top`, `free`, and `du` commands help administrators analyze system resources and identify resource-intensive processes or directories.

---

# top Command

The `top` command displays a real-time view of the system, including running processes, CPU usage, memory usage, and other system information.

## Basic Syntax

```bash
top
```

### Basic Usage

```bash
top
```

### Explanation

- Displays live system information.
- Shows CPU usage, memory usage, running tasks, and process details.
- Refreshes automatically every few seconds.

---

# Sorting Processes in top

While `top` is running, the following shortcut keys can be used:

| Key | Function |
|------|----------|
| `M` | Sort processes by memory usage |
| `P` | Sort processes by CPU usage |
| `R` | Reverse the current sorting order |

---

# Changing the Update Interval

By default, `top` refreshes every **3 seconds**.

### Update Every Second

```bash
top -d 1
```

### Explanation

- `-d` specifies the delay between updates.
- `1` updates the display every one second.

---

# Display Specific User's Processes

```bash
top -u username
```

### Explanation

Displays only the processes belonging to the specified user.

---

# Display Active Processes

```bash
top -i
```

### Explanation

Hides idle processes and displays only active processes.

---

# Killing a Process from top

While `top` is running:

1. Press `k`
2. Enter the PID
3. Press **Enter**

Equivalent commands from the terminal:

Normal Kill

```bash
kill PID
```

Force Kill

```bash
kill -9 PID
```

Kill by Process Name

```bash
pkill process_name
```

---

# free Command

The `free` command displays a snapshot of the system's memory usage.

## Basic Syntax

```bash
free
```

### Explanation

Displays information about:

- Total physical RAM
- Used memory
- Free memory
- Shared memory
- Buffers and cache
- Available memory

---

# Memory Fields

| Field | Description |
|--------|-------------|
| Total | Total physical RAM available |
| Used | Memory currently in use |
| Free | Completely unused RAM |
| Shared | Memory used by temporary files |
| Buff/Cache | Memory used for buffers and cache |
| Available | Estimated memory available for new applications |

---

# Common Options

### Human Readable Format

```bash
free -h
```

---

### Display in Megabytes

```bash
free -m
```

---

### Display in Gigabytes

```bash
free -g
```

---

# Continuous Monitoring

```bash
free -h -s 3 -c 5
```

### Explanation

| Option | Purpose |
|--------|----------|
| `-h` | Human readable output |
| `-s 3` | Update every 3 seconds |
| `-c 5` | Stop after 5 updates |

---

# Display Total Memory

```bash
free -h -t
```

### Explanation

Displays an additional line showing total memory including swap.

---

# du Command

The `du` (Disk Usage) command estimates file and directory disk usage.

## Basic Syntax

```bash
du
```

---

# Human Readable Output

```bash
du -h
```

---

# Check Disk Usage of a Directory

```bash
du -h ./documents
```

Example Output

```text
0       ./documents/reports
10M     ./documents/logscripts
```

### Explanation

Shows how much disk space files and directories occupy.

---

# Investigating Specific Directories

Current Directory Only

```bash
du -h --max-depth=0
```

### Explanation

Shows only the current directory size.

---

One Level Deep

```bash
du -h --max-depth=1
```

### Explanation

Shows only immediate subdirectories.

---

# Sorting Disk Usage

```bash
du -h | sort -h
```

### Explanation

- `du -h` displays sizes in human-readable format.
- `sort -h` sorts sizes numerically while understanding units like K, M, and G.

---

# Finding Large Files

Run `du` Once Per File

```bash
find . -type f -exec du -h {} \;
```

### Explanation

Runs `du` separately for every file.

---

Run `du` with Multiple Files

```bash
find . -type f -exec du -h {} +
```

### Explanation

Collects multiple files and executes a single `du` command, making it more efficient.

---

# Find Largest Files

```bash
find . -type f -exec du -h {} + | sort -hr | head -n 5
```

### Explanation

- Finds all files.
- Calculates their sizes.
- Sorts them in descending order.
- Displays the five largest files.

---

# Find Files Larger Than 1 MB

```bash
find . -type f -size +1M -exec du -h {} + | sort -hr
```

### Explanation

Lists files larger than 1 MB and sorts them by size.

---

# Generate Disk Usage Report

```bash
du -h --max-depth=2 | sort -hr > report.txt
```

### Explanation

Generates a sorted disk usage report and saves it into `report.txt`.

---

# Useful du Options

| Command | Description |
|---------|-------------|
| `du -s` | Display summary only |
| `du -ah` | Include files along with directories |
| `du -ch dir1 dir2` | Display grand total |
| `du -h -t 100M` | Show only entries greater than or equal to 100 MB |

---

# Practical Applications

- Monitor CPU and memory usage
- Identify memory-intensive processes
- Kill unresponsive processes
- Monitor RAM continuously
- Analyze directory sizes
- Locate large files
- Generate disk usage reports
- Sort storage usage for cleanup

---

# Key Takeaways

- `top` provides real-time process and system monitoring.
- Use `M`, `P`, and `R` to sort processes inside `top`.
- `free` displays memory usage and supports continuous monitoring.
- `du` estimates disk usage for files and directories.
- `find`, `du`, `sort`, and `head` can be combined to identify large files quickly.
- `sort -h` correctly sorts human-readable file sizes.
