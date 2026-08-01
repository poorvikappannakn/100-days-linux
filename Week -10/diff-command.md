# diff Command

The `diff` command is used to compare two files or directories line by line and display the differences between them. It is commonly used to identify changes in text files, source code, and configuration files.

---

# Syntax

```bash
diff [OPTION] FILE1 FILE2
```

---

# Common Options

| Option | Description |
|---------|-------------|
| `-u` | Display output in unified format |
| `-w` | Ignore whitespace differences |
| `-r` | Compare directories recursively |

---

# Basic File Comparison

```bash
diff file1.txt file2.txt
```

Displays the differences between the two files.

---

# Understanding diff Output

Example Output

```text
3c3
< Linux
---
> Unix
```

### Meaning

- `a` → Add
- `c` → Change
- `d` → Delete

---

# Example: Addition

```text
4a5
> New Line
```

Means a new line has been added after line 4.

---

# Example: Deletion

```text
5d4
< Old Line
```

Means line 5 from the first file has been deleted.

---

# Example: Change

```text
2c2
< Hello
---
> Hi
```

Means line 2 has been changed.

---

# Unified Format

Displays changes in a more readable format.

```bash
diff -u file1.txt file2.txt
```

Example Output

```text
--- file1.txt
+++ file2.txt
@@
-Hello
+Hi
```

---

# Ignore Whitespace Differences

```bash
diff -w file1.txt file2.txt
```

Ignores spaces and tabs while comparing files.

---

# Comparing Source Code Files

```bash
diff old_version.cpp new_version.cpp
```

Useful for checking modifications between different versions of source code.

---

# Comparing Directories

Compare all files inside two directories recursively.

```bash
diff -r directory1 directory2
```

The `-r` option compares every file and subdirectory.

---

# Combining diff with Other Commands

Save the comparison result into another file.

```bash
diff file1.txt file2.txt > changes.txt
```

---

# Key Learnings

- Compare two files line by line.
- Understand the meaning of `a`, `c`, and `d`.
- Display output in unified format.
- Ignore whitespace differences.
- Compare directories recursively.
- Compare different versions of source code.
- Save comparison results into a file.
