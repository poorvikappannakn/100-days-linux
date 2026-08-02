# join Command

The `join` command is used to combine two sorted files based on a common field. It is similar to an SQL INNER JOIN and merges records that have matching values.

---

# Syntax

```bash
join [OPTION]... FILE1 FILE2
```

---

# Important Rule

Both files **should be sorted** on the join field before using `join`.

Default sorting is based on **field 1**.

Example:

```bash
sort file1.txt > file1_sorted.txt
sort file2.txt > file2_sorted.txt

join file1_sorted.txt file2_sorted.txt
```

---

# Basic Example

### employees.txt

```text
1001 John Engineering
1002 Sarah Marketing
1003 Mike Sales
1004 Emily HR
1005 David Finance
```

### departments.txt

```text
Engineering ENG
Marketing MKT
Sales SLS
HR HRS
Finance FIN
IT ITS
```

Join the files.

```bash
join -1 3 -2 1 employees.txt departments.txt
```

### Explanation

- `-1 3` → Use **field 3** from file1.
- `-2 1` → Use **field 1** from file2.

---

# Selecting Different Join Fields

Join using field 2 from file1 and field 3 from file2.

```bash
join -1 2 -2 3 file1.txt file2.txt
```

### Remember

If you write

```bash
join -1 X -2 Y file1 file2
```

then

- File1 should be sorted by field **X**
- File2 should be sorted by field **Y**

---

# Customizing the Output

The `-o` option specifies which fields should be displayed.

```bash
join -o 1.2,1.3,2.2 employees.txt salaries.txt
```

### Understanding the Format

```
file.field
```

Examples

| Field | Meaning |
|--------|---------|
| `1.1` | Field 1 from file1 |
| `1.2` | Field 2 from file1 |
| `1.3` | Field 3 from file1 |
| `2.1` | Field 1 from file2 |
| `2.2` | Field 2 from file2 |

Example

```bash
join -o 1.2,2.2 file1 file2
```

Output

```
John 80000
Sarah 65000
```

Only the requested fields are displayed.

---

# Including Unmatched Records

Normally `join` behaves like an **INNER JOIN** and prints only matching records.

To include unmatched records from file1:

```bash
join -a 1 employees.txt salaries.txt
```

To include unmatched records from file2:

```bash
join -a 2 employees.txt salaries.txt
```

---

# Sorting Before Joining

Default sorting

```bash
sort file1.txt
sort file2.txt
```

Sorting using a different field

```bash
sort -k3 employees.txt
sort -k1 departments.txt
```

Then

```bash
join -1 3 -2 1 employees.txt departments.txt
```

---

# Key Learnings

- Join combines two files using a common field.
- By default, the first field is used for joining.
- `-1` specifies the join field of file1.
- `-2` specifies the join field of file2.
- `-o` customizes which fields are printed.
- `-a` includes unmatched records from one file.
- Files should be sorted on their respective join fields before joining.
- Think of `join` as similar to an SQL INNER JOIN.
