# Wildcard Pattern Matching

## Overview

Wildcards allow users to match multiple files using special pattern characters.

---

## Asterisk (*)

Matches zero or more characters.

### Example

```bash
ls *.txt
```

Matches:

```
notes.txt
file.txt
hello.txt
```

---

## Question Mark (?)

Matches exactly one character.

### Example

```bash
ls file?.txt
```

Matches:

```
file1.txt
file2.txt
```

Does not match:

```
file10.txt
```

---

## Character Set []

Matches any one character inside the brackets.

### Example

```bash
ls file[13].txt
```

Matches:

```
file1.txt
file3.txt
```

---

## Character Range

### Example

```bash
ls file[a-p]*.txt
```

Matches files beginning with letters from a to p.

---

## Brace Expansion

Creates multiple files at once.

### Examples

```bash
touch note{1..5}.txt

touch {a,b,c}-{1..24}.txt
```

---

## Learning Outcome

- Wildcard matching
- Character ranges
- Brace expansion
- Efficient file creation
