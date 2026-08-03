# AWK Command in Linux

## 📌 Overview

`AWK` is a powerful text-processing and pattern-scanning tool used to extract, filter, analyze, and generate reports from structured text files.

**AWK** is named after its creators:

- **A** → Alfred Aho
- **W** → Peter Weinberger
- **K** → Brian Kernighan

---

# Basic Syntax

## Inline Script

```bash
awk 'program' input_file
```

Example

```bash
awk '{print $1}' students.txt
```

---

## Script File

```bash
awk -f script.awk input_file
```

Example

```bash
awk -f script.awk students.txt
```

The `-f` option tells AWK to read the program from a separate file.

---

# Basic Structure

```bash
awk 'pattern { action }' file
```

Both **pattern** and **action** are optional.

---

# Printing Entire Line

```bash
awk '{print}' file.txt
```

or

```bash
awk '{print $0}' file.txt
```

`$0` represents the entire line.

---

# Printing Specific Fields

Suppose `students.txt`

```text
John 85 CS
Alice 92 IT
Bob 78 EC
```

Print first field

```bash
awk '{print $1}' students.txt
```

Output

```text
John
Alice
Bob
```

---

Print second field

```bash
awk '{print $2}' students.txt
```

Output

```text
85
92
78
```

---

Print multiple fields

```bash
awk '{print $1,$3}' students.txt
```

Output

```text
John CS
Alice IT
Bob EC
```

---

# Field Variables

| Variable | Meaning |
|----------|---------|
| `$0` | Entire line |
| `$1` | First field |
| `$2` | Second field |
| `$3` | Third field |
| `$NF` | Last field |
| `NR` | Current record number |
| `NF` | Number of fields |

---

# Using Custom Delimiter

Default delimiter is whitespace.

To use another delimiter:

```bash
awk -F ':' '{print $1}' passwd.txt
```

`-F` specifies the field separator.

---

# Pattern Matching

Print only Engineering employees

```bash
awk '/Engineering/' employees.txt
```

---

Print lines containing "ERROR"

```bash
awk '/ERROR/' server.log
```

---

# Conditional Statements

Print students scoring above 80

```bash
awk '$2 > 80' students.txt
```

---

Print employees whose salary exceeds 50000

```bash
awk '$3 > 50000' employees.txt
```

---

# BEGIN Block

Executed once before reading the input file.

Example

```bash
awk 'BEGIN {print "Student Report"} {print $1}' students.txt
```

Output

```text
Student Report
John
Alice
Bob
```

---

# END Block

Executed after processing all input.

Example

```bash
awk '{sum += $2} END {print sum}' students.txt
```

---

# Variables

Assign variables

```bash
awk '{sum += $2}'
```

Display result

```bash
awk '{sum += $2} END {print sum}'
```

Average

```bash
awk '{sum += $2} END {print sum/NR}'
```

---

# Associative Arrays

Count occurrences

Example

```bash
awk '{count[$1]++} END {for(i in count) print i,count[i]}' file.txt
```

---

# Built-in Variables

| Variable | Description |
|----------|-------------|
| `NR` | Current record number |
| `NF` | Number of fields |
| `FS` | Input field separator |
| `OFS` | Output field separator |

---

# Changing Output Separator

```bash
awk 'BEGIN {OFS=","} {print $1,$2}' students.txt
```

---

# Practical Examples

Print usernames from `/etc/passwd`

```bash
awk -F ':' '{print $1}' /etc/passwd
```

---

Print username and shell

```bash
awk -F ':' '{print $1,$7}' /etc/passwd
```

---

Display line numbers

```bash
awk '{print NR,$0}' file.txt
```

---

Count total lines

```bash
awk 'END {print NR}' file.txt
```

---

Count words

```bash
awk '{count += NF} END {print count}' file.txt
```

---

# Commonly Used Options

| Option | Description |
|---------|-------------|
| `-F` | Specify input field separator |
| `-f` | Read AWK program from file |
| `BEGIN` | Execute before input |
| `END` | Execute after input |

---

# Applications

- Log analysis
- Report generation
- Data extraction
- Filtering records
- Text processing
- Counting and summarizing data
- CSV file processing
- Linux administration

---

# Key Takeaways

- AWK is a pattern scanning and text-processing language.
- Fields are accessed using `$1`, `$2`, `$3`, etc.
- `$0` represents the entire record.
- `-F` changes the input delimiter.
- `BEGIN` executes before processing.
- `END` executes after processing.
- Associative arrays make counting and grouping easy.
- Frequently used in Linux administration, scripting, and cybersecurity.
