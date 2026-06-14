# Grep and Kernel Logs

## Commands Practiced

```bash
grep "pattern" file

grep -w "joker" /etc/passwd

dmesg

dmesg | grep error

sudo dmesg | grep -iE "fail|error"
```

---

## grep

General syntax:

```bash
grep [options] "pattern" filename
```

Used to search text matching a pattern.

---

## Exact Match

```bash
grep -w "joker" /etc/passwd
```

Flag:

```text
-w = exact word match
```

---

## dmesg

```bash
dmesg
```

Displays kernel messages.

Useful for:

- Boot logs
- Hardware detection
- Driver issues
- System errors

---

## Pipe Operator

```bash
|
```

Passes output of one command as input to another.

Example:

```bash
dmesg | grep error
```

---

## Regular Expressions

```bash
grep -E "fail|error"
```

Flag:

```text
-E = Extended Regular Expressions
```

Meaning:

```text
fail OR error
```

---

## Case Insensitive Search

```bash
grep -i "error"
```

Flag:

```text
-i = ignore case
```

---

## Combined Example

```bash
sudo dmesg | grep -iE "fail|error"
```

Searches kernel messages for failures or errors.

---

## Key Learnings

- Used grep for text searching.
- Learned exact matching.
- Used regular expressions.
- Understood shell pipes.
- Examined kernel logs using dmesg.
