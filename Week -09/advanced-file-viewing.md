# Advanced File Viewing Commands

## Introduction

Linux provides advanced file viewing commands that allow users to display specific parts of a file, number lines, and combine commands to efficiently filter and inspect data. These commands are especially useful when working with large files and log files.

---

# `head`

## Introduction

The `head` command displays the first **10 lines** of a file by default.

## Syntax

```bash
head [OPTION] FILE
```

---

## Common Options

### `-n` (Number of Lines)

Displays the first **N** lines.

```bash
head -n 5 file.txt
```

---

### `-c` (Number of Bytes)

Displays the first **N** bytes of a file.

```bash
head -c 100 file.txt
```

---

### `-q` (Quiet)

Suppresses file name headers when multiple files are displayed.

```bash
head -q file1.txt file2.txt
```

---

### `-v` (Verbose)

Always displays file name headers.

```bash
head -v file.txt
```

---

## Example

```bash
head students.txt
```

### Example Output

```text
Rahul
Ankit
Priya
Rohan
Sneha
...
```

---

## Use Cases

- Preview the beginning of large files.
- View configuration files.
- Inspect the first few log entries.

---

## Key Points

- Displays the first 10 lines by default.
- Can display a specified number of lines or bytes.
- Useful for quickly checking file contents.

---

# `tail`

## Introduction

The `tail` command displays the last **10 lines** of a file by default.

## Syntax

```bash
tail [OPTION] FILE
```

---

## Common Options

### `-n` (Number of Lines)

Displays the last **N** lines.

```bash
tail -n 20 file.txt
```

---

### `-f` (Follow)

Continuously displays newly added content.

```bash
tail -f server.log
```

---

## Example

```bash
tail students.txt
```

### Example Output

```text
Arun
Nisha
Kiran
Manoj
Deepa
```

---

## Use Cases

- Monitor log files.
- View recently added records.
- Check the end of large files.

---

## Key Points

- Displays the last 10 lines by default.
- `-f` is commonly used for real-time log monitoring.
- Frequently used by system administrators.

---

# `nl`

## Introduction

The `nl` command displays a file with line numbers.

## Syntax

```bash
nl [OPTION] FILE
```

---

## Common Options

### `-b`

Controls which lines are numbered.

```bash
nl -b a file.txt
```

---

### `-n`

Specifies the numbering format.

```bash
nl -n rz file.txt
```

---

### `-s`

Specifies the separator between the line number and text.

```bash
nl -s ":" file.txt
```

---

### `-w`

Sets the width of the line number field.

```bash
nl -w 4 file.txt
```

---

## Example

```bash
nl notes.txt
```

### Example Output

```text
     1  Linux
     2  Ubuntu
     3  Fedora
```

---

## Use Cases

- Reading source code.
- Reviewing documentation.
- Referencing specific lines.

---

## Key Points

- Numbers non-empty lines by default.
- Supports multiple numbering formats.
- Useful for debugging and documentation.

---

# Combining Commands

## `grep` with `head`

Displays the **first few matching lines**.

### Syntax

```bash
grep "pattern" file.txt | head
```

### Example

```bash
grep "error" server.log | head -5
```

### Use Case

Quickly view the first matching records in a large file.

---

## `grep` with `tail`

Displays the **last few matching lines**.

### Syntax

```bash
grep "pattern" file.txt | tail
```

### Example

```bash
grep "error" server.log | tail -5
```

### Use Case

View the latest matching records in log files.

---

# When to Use Each Command

| Command | Best Use |
|----------|----------|
| `head` | View the beginning of a file |
| `tail` | View the end of a file or monitor logs |
| `nl` | Display files with line numbers |
| `grep \| head` | Display the first matching records |
| `grep \| tail` | Display the latest matching records |

---

# Key Points

- `head` displays the beginning of a file.
- `tail` displays the end of a file and can monitor changes using `-f`.
- `nl` displays files with line numbers.
- `grep | head` shows the first matching lines.
- `grep | tail` shows the latest matching lines.
- These commands are commonly used for log analysis and quick file inspection.
