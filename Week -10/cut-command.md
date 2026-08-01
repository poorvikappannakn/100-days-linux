# cut Command

The `cut` command is used to extract specific portions of text from each line of a file. It works with delimiter-separated fields, fixed-width columns, or specific character positions.

---

# Syntax

```bash
cut [OPTION]... [FILE]
```

---

# Common Options

| Option | Description |
|---------|-------------|
| `-d` | Specify the delimiter |
| `-f` | Extract specific field(s) |
| `-c` | Extract specific character position(s) |
| `-s` | Skip lines without the specified delimiter |

---

# Searching Lines Containing Both Words

To display lines containing **Apple** or **apple**:

```bash
grep "Apple" filename
grep "apple" filename
```

---

# Extracting a Single Field

Suppose fields are separated by commas.

```bash
cut -d ',' -f 1 filename
```

**Explanation**

- `-d ','` specifies comma as the delimiter.
- `-f 1` extracts the first field.

---

# Displaying Data Without the First Line

Display all lines starting from the second line.

```bash
tail -n +2 filename
```

**Explanation**

- `+2` means start displaying from line 2 until the end.

---

# Last N Lines

Display the last 3 lines.

```bash
tail -n 3 filename
```

---

# Extracting Multiple Fields

Extract field 2 and field 3.

```bash
cut -d ',' -f 2,3 filename
```

---

# Extracting a Range of Fields

Extract fields 1 through 3.

```bash
cut -d ',' -f 1-3 filename
```

---

# Working with Fixed-Width Columns

Sometimes data is arranged in fixed-width columns rather than being separated by delimiters.

Example:

```text
ISBN       Title                Quantity
1234567890 The Great Adventure      100
2345678901 Mystery in the Hills       75
```

Extract only the title column.

```bash
cut -c 11-25 filename
```

**Explanation**

- `-c` extracts character positions.
- Characters 11–25 contain the title.

---

# Combining grep and cut

Extract the second field from lines matching a pattern.

```bash
grep -E '[0-9]{2}:[0-9]{2}' filename | cut -d ',' -f 2
```

---

# Skip Lines Without Delimiter

```bash
cut -d ',' -s -f 2 filename
```

**Explanation**

- `-s` suppresses lines that do not contain the delimiter.

---

# Key Learnings

- Extract fields using delimiters.
- Extract multiple fields and field ranges.
- Work with fixed-width columns.
- Skip unwanted lines using `-s`.
- Combine `cut` with other Linux commands like `grep` and `tail`.
