# tr Command

The `tr` (translate) command is used to translate, replace, delete, or squeeze repeated characters from the standard input.

> **Note:** `tr` does not accept a filename directly. It works with standard input using pipes (`|`) or input redirection (`<`).

---

# Syntax

```bash
tr [OPTION] SET1 [SET2]
```

---

# Common Options

| Option | Description |
|---------|-------------|
| `-d` | Delete specified characters |
| `-s` | Squeeze repeated characters |
| `-t` | Truncate SET1 to match the length of SET2 |

---

# Convert Lowercase to Uppercase

```bash
echo "hello world" | tr 'a-z' 'A-Z'
```

**Output**

```text
HELLO WORLD
```

---

# Convert Uppercase to Lowercase

```bash
echo "HELLO WORLD" | tr 'A-Z' 'a-z'
```

**Output**

```text
hello world
```

---

# Replace Characters

Replace every `a` with `x`.

```bash
echo "banana" | tr 'a' 'x'
```

**Output**

```text
bxnxnx
```

---

# Delete Characters

Delete all vowels.

```bash
echo "Linux Command Line" | tr -d 'aeiouAEIOU'
```

**Output**

```text
Lnx Cmmnd Ln
```

---

# Delete Digits

```bash
echo "abc123xyz456" | tr -d '[:digit:]'
```

**Output**

```text
abcxyz
```

---

# Squeeze Repeated Characters

Remove consecutive duplicate spaces.

```bash
echo "Linux     Command      Line" | tr -s ' '
```

**Output**

```text
Linux Command Line
```

---

# Squeeze Repeated Characters (Example)

```bash
echo "aaabbbbcccc" | tr -s 'abc'
```

**Output**

```text
abc
```

---

# Truncate Character Sets

```bash
echo "abcdef" | tr -t 'abcdef' 'XYZ'
```

**Output**

```text
XYZdef
```

**Explanation**

- `-t` truncates **SET1** to match the length of **SET2**.
- Only `a`, `b`, and `c` are translated.

---

# Character Classes

Convert lowercase letters to uppercase.

```bash
echo "linux commands" | tr '[:lower:]' '[:upper:]'
```

---

# Combining tr with Other Commands

Convert the contents of a file to uppercase.

```bash
cat filename | tr 'a-z' 'A-Z'
```

---

# Key Learnings

- Convert lowercase to uppercase and vice versa.
- Replace one set of characters with another.
- Delete unwanted characters.
- Delete digits using character classes.
- Compress repeated characters.
- Truncate character sets.
- Use `tr` with pipes for text processing.
