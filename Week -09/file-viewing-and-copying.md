# File Viewing and Copying in Linux

## Introduction

Linux provides several commands to copy files and view their contents. Depending on the size of the file and the required functionality, different commands are preferred.

---

# Copying Files with `cp`

## Syntax

```bash
cp [OPTION] SOURCE DESTINATION
```

---

## Common Options

### `-u` (Update)

Copies the file only if:

- The source file is newer than the destination.
- The destination file does not exist.

```bash
cp -u file1.txt backup/
```

---

### `-v` (Verbose)

Displays every file being copied.

```bash
cp -v file1.txt backup/
```

Example Output

```text
'file1.txt' -> 'backup/file1.txt'
```

---

### `-n` (No Clobber)

Never overwrite an existing file.

```bash
cp -n report.txt backup/
```

---

### `-l` (Hard Link)

Creates a hard link instead of copying the file.

```bash
cp -l original.txt hardlink.txt
```

---

### `-s` (Symbolic Link)

Creates a symbolic link instead of copying.

```bash
cp -s original.txt symlink.txt
```

---

# Displaying File Contents

## `cat`

Displays the entire contents of a file.

```bash
cat file.txt
```

Useful for small files.

---

### `cat -E`

Displays a `$` symbol at the end of every line.

```bash
cat -E file.txt
```

Example

```text
Linux$
Ubuntu$
Fedora$
```

---

# Viewing Large Files

## `more`

Displays one screen at a time.

```bash
more file.txt
```

### Navigation

| Key | Action |
|------|--------|
| Space | Next page |
| Enter | Next line |
| q | Quit |

---

## Start from a Specific Line

```bash
more +50 file.txt
```

Starts displaying from line 50.

---

## Display a Fixed Number of Lines

```bash
more -5 file.txt
```

Displays five lines at a time.

---

## Search Before Opening

```bash
more +/Hello file.txt
```

Starts near the first occurrence of **Hello**.

---

# `less`

`less` is an advanced version of `more`.

It allows:

- Forward navigation
- Backward navigation
- Searching while reading
- Efficient viewing of very large files

---

## Opening a File

```bash
less file.txt
```

---

## Navigation

| Key | Action |
|------|--------|
| Space | Next page |
| b / Page Up | Previous page |
| Page Down | Next page |
| ↑ ↓ | Move line by line |
| g | Beginning of file |
| G | End of file |
| q | Quit |

---

## Searching

Search forward

```bash
/Error
```

Next occurrence

```text
n
```

Previous occurrence

```text
N
```

---

## Display Line Numbers

```bash
less -N file.txt
```

---

## Search Before Opening

```bash
less +/Error server-log.txt
```

The file opens near the first occurrence of **Error**.

---

# When to Use Each Command

| Command | Best Use |
|----------|----------|
| `cat` | Small files |
| `more` | Read large files with simple forward navigation |
| `less` | Large files requiring searching and full navigation |

---

# Key Points

- `cp` copies files and supports update, verbose, no-clobber, hard-link, and symbolic-link options.
- `cat` prints the entire file.
- `cat -E` shows the end of each line using `$`.
- `more` displays files one page at a time.
- `less` is an advanced pager supporting backward navigation and searching.
- `less` is generally preferred over `more` for large files.
