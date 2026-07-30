# Text Searching with `grep`

The `grep` (Global Regular Expression Print) command is used to search for a specific pattern or text inside one or more files.

---

# Basic Syntax

```bash
grep "PATTERN" filename
```

### Example

```bash
grep "ERROR" server.log
```

Displays all lines containing the word **ERROR**.

---

# Counting Matching Lines

```bash
grep -c "PATTERN" filename
```

### Example

```bash
grep -c "ERROR" server.log
```

Displays only the number of matching lines.

---

# Case-Insensitive Search

```bash
grep -i "PATTERN" filename
```

### Example

```bash
grep -i "error" server.log
```

Matches `ERROR`, `Error`, `error`, etc.

---

# Count Matches (Case-Insensitive)

```bash
grep -ic "PATTERN" filename
```

### Example

```bash
grep -ic "error" server.log
```

Counts all matching lines while ignoring letter case.

---

# Searching Multiple Files

```bash
grep "database connection failed" logs/*
```

Searches every file inside the `logs` directory.

### Example Output

```text
logs/errors.log: database connection failed
logs/server.log: database connection failed
```

---

# Using Regular Expressions

`grep` supports regular expressions for pattern matching.

### Example

```bash
grep "2023-[0-9][0-9]-[0-9][0-9]" logs/server.log
```

Matches dates such as

```text
2023-07-15
2023-12-01
```

### Explanation

- `[0-9]` → Matches any digit from 0 to 9.
- `[0-9][0-9]` → Matches any two-digit number.

---

# Fixed String Search

```bash
grep -F "2023-[0-9][0-9]" logs/server.log
```

### Explanation

`-F` treats the pattern as plain text instead of a regular expression.

Useful when searching for characters like:

```text
[]
()
+
*
?
```

without interpreting them as regex symbols.

---

# Displaying Context

Shows lines before and after the matching line.

### Syntax

```bash
grep -B 2 -A 2 "CRITICAL" logs/server.log
```

### Explanation

- `-B 2` → Shows 2 lines **before** the match.
- `-A 2` → Shows 2 lines **after** the match.

---

# Invert Match

```bash
grep -v "ERROR" logs/server.log
```

Displays all lines that **do not** contain the word `ERROR`.

---

# Other Useful Flags

## Show Line Numbers

```bash
grep -n "PATTERN" filename
```

Displays matching lines along with their line numbers.

---

## Recursive Search

```bash
grep -r "PATTERN" directory/
```

Searches all files inside the directory and its subdirectories.

---

## Show Matching File Names Only

```bash
grep -l "PATTERN" *.txt
```

Displays only the names of files containing the pattern.

---

## Match Whole Word Only

```bash
grep -w "apple" filename
```

Matches only the complete word `apple`.

Will **not** match:

```text
pineapple
apples
```

---

## Extended Regular Expressions

```bash
grep -E "cat|dog" animals.txt
```

Uses extended regular expressions.

The `|` operator means **OR**.

Matches either:

```text
cat
dog
```

---

# Basic vs Extended Regular Expressions

## Basic Regular Expressions (BRE)

Some special characters need to be escaped.

Example:

```text
\+
\?
\|
\(
\)
```

---

## Extended Regular Expressions (ERE)

Special characters can be used directly.

Example:

```text
+
?
|
(
)
```

Use the `-E` option to enable extended regular expressions.

---

# Using Multiple `grep` Commands

You can combine multiple `grep` commands using a pipe (`|`).

### Example

```bash
grep "Apple" filename | grep "Ball"
```

### Explanation

1. The first `grep` searches for lines containing **Apple**.
2. The output is passed to the second `grep`.
3. The second `grep` keeps only the lines that also contain **Ball**.

This returns only the lines containing **both** words.

---

# Summary

## Common `grep` Options

| Option | Description |
|---------|-------------|
| `-c` | Count matching lines |
| `-i` | Ignore case |
| `-ic` | Ignore case and count matches |
| `-F` | Treat pattern as plain text |
| `-B` | Show lines before match |
| `-A` | Show lines after match |
| `-v` | Show non-matching lines |
| `-n` | Display line numbers |
| `-r` | Search recursively |
| `-l` | Display matching file names only |
| `-w` | Match whole word only |
| `-E` | Use extended regular expressions |
