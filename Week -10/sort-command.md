# sort Command

The `sort` command is used to arrange the contents of a file in alphabetical, numerical, or custom order. It can also sort data based on one or more fields.

---

# Syntax

```bash
sort [OPTION]... [FILE]
```

---

# Common Options

| Option | Description |
|---------|-------------|
| `-n` | Sort numerically |
| `-r` | Reverse the sorting order |
| `-t` | Specify the field delimiter |
| `-k` | Sort using a specific field |
| `-u` | Remove duplicate lines |
| `-f` | Ignore case while sorting |
| `-o` | Write output to a file |
| `-c` | Check if the file is already sorted |
| `-b` | Ignore leading blanks |

---

# Alphabetical Sorting

Sort the contents of a file alphabetically.

```bash
sort filename
```

---

# Numerical Sorting

Sort numbers from lowest to highest.

```bash
sort -n -t ':' -k2 filename
```

**Explanation**

- `-n` → Treat the field as a number.
- `-t ':'` → Use `:` as the delimiter.
- `-k2` → Sort using the second field.

---

# Reverse Sorting

Sort in descending order.

```bash
sort -nr -t ':' -k2 filename
```

---

# Sorting Using Multiple Fields

If two records have the same value in the second field, sort them using the third field.

```bash
sort -t ':' -k2 -k3 filename
```

**Explanation**

- First sort using field 2.
- If field 2 is equal, sort using field 3.

Example

```text
David Lee:78:97
Alice:18:92
Mark:19:90
```

---

# Removing Duplicate Entries

Remove duplicate lines.

```bash
sort -u students.txt
```

Example

Input

```text
Alice : Chess Club
Bob : Cricket Club
Alice : Chess Club
Bob : Math Club
```

Output

```text
Alice : Chess Club
Bob : Cricket Club
Bob : Math Club
```

---

# Ignore Case While Sorting

```bash
sort -f filename
```

---

# Save Sorted Output to Another File

```bash
sort -o sorted.txt filename
```

---

# Check if a File is Already Sorted

```bash
sort -c filename
```

---

# Ignore Leading Blanks

```bash
sort -b filename
```

---

# Key Learnings

- Perform alphabetical and numerical sorting.
- Sort using specific fields.
- Sort using multiple keys.
- Reverse sorting order.
- Remove duplicate entries.
- Ignore case while sorting.
- Save sorted output to another file.
- Check whether a file is already sorted.
```
