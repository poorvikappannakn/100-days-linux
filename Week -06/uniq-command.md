# Uniq Command

## Overview

The `uniq` command is used to display the contents of a file after removing **consecutive duplicate lines**.

> **Note:** The `uniq` command **does not modify the original file**. It only displays the processed output on the terminal unless the output is redirected to another file.

---

## Basic Syntax

```bash
uniq filename
```

### Example

Suppose the file `a` contains:

```text
apple
apple
banana
banana
cat
dog
dog
```

Command:

```bash
uniq a
```

Output:

```text
apple
banana
cat
dog
```

The original file `a` remains unchanged.

---

# Important Concept

The `uniq` command removes **only consecutive duplicate lines**.

If duplicate entries are **not adjacent**, `uniq` will not remove them.

### Example

Suppose the file `a` contains:

```text
apple
banana
apple
cat
banana
dog
```

Command:

```bash
uniq a
```

Output:

```text
apple
banana
apple
cat
banana
dog
```

Nothing changes because the duplicate lines are not consecutive.

---

# Why Sort Before Using Uniq?

Since `uniq` only removes consecutive duplicate lines, duplicate entries should first be placed together using the `sort` command.

### Step 1

```bash
sort a
```

Output:

```text
apple
apple
banana
banana
cat
dog
```

### Step 2

```bash
sort a | uniq
```

Output:

```text
apple
banana
cat
dog
```

Here,

* `sort` arranges identical entries together.
* `uniq` removes the consecutive duplicate lines.

---

# Command Options

> **Important:** All `uniq` options (`-c`, `-d`, and `-u`) also work only on **consecutive duplicate lines**. If the file is not sorted, duplicate entries that are separated by other lines will not be treated as duplicates.

---

## Count Duplicate Lines

```bash
uniq -c filename
```

Displays the number of occurrences of each **consecutive** duplicate line.

### Example

Input:

```text
apple
apple
banana
banana
banana
cat
```

Command:

```bash
uniq -c a
```

Output:

```text
2 apple
3 banana
1 cat
```

---

## Display Only Duplicate Lines

```bash
uniq -d filename
```

Displays only the **consecutive duplicated** entries.

### Example

Input:

```text
apple
apple
banana
banana
cat
```

Output:

```text
apple
banana
```

---

## Display Only Unique Lines

```bash
uniq -u filename
```

Displays only the lines that appear exactly once (i.e., they are not part of any consecutive duplicate group).

### Example

Input:

```text
apple
apple
banana
banana
cat
dog
```

Output:

```text
cat
dog
```

---

# Common Usage

```bash
sort filename | uniq
```

Sorts the contents of the file and removes duplicate entries.

---

```bash
sort filename | uniq -c
```

Sorts the file and displays the count of each unique entry.

---

```bash
sort filename | uniq -d
```

Sorts the file and displays only duplicate entries.

---

```bash
sort filename | uniq -u
```

Sorts the file and displays only unique entries.

---

# Summary

| Command             | Description                                                   |
| ------------------- | ------------------------------------------------------------- |
| `uniq file`         | Displays the file after removing consecutive duplicate lines. |
| `uniq -c file`      | Displays the count of consecutive duplicate lines.            |
| `uniq -d file`      | Displays only consecutive duplicated lines.                   |
| `uniq -u file`      | Displays only lines that appear exactly once.                 |
| `sort file \| uniq` | Sorts the file and removes duplicate entries.                 |

---

# Learning Outcome

* Understand how the `uniq` command works.
* Learn why duplicate lines must be consecutive.
* Understand why `sort` is commonly used before `uniq`.
* Count duplicate entries using `uniq -c`.
* Display duplicate entries using `uniq -d`.
* Display unique entries using `uniq -u`.
* Apply `sort` and `uniq` together for effective duplicate handling.
