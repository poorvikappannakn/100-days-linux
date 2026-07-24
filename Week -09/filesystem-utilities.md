# Filesystem Utilities

This section covers commonly used Linux utilities for listing files, visualizing directory structures, and displaying file statistics.

---

# ls (List Directory Contents)

The `ls` command displays files and directories.

---

## Human Readable File Sizes

```bash
ls -lh
```

Displays file sizes in a human-readable format (KB, MB, GB).

Example:

```text
-rw-r--r-- 1 user user 2.1K notes.txt
-rw-r--r-- 1 user user 15M movie.mp4
```

---

## Recursive Listing

```bash
ls -R
```

Lists all directories and their contents recursively.

Useful for viewing the complete directory structure.

---

## Display Hidden Files

```bash
ls -a
```

Displays all files, including hidden files (files beginning with `.`).

Example:

```text
.bashrc
.profile
.gitignore
```

---

## Sort by Modification Time

```bash
ls -lt
```

Lists files sorted by the most recently modified file first.

---

## Reverse Order

```bash
ls -ltr
```

Lists files sorted by the oldest modified file first.

---

## Sort by File Size

```bash
ls -lS
```

Lists files from largest to smallest.

---

## Sort by File Extension

```bash
ls -X
```

Groups files according to their extensions.

Example:

```text
image.jpg
notes.txt
program.py
video.mp4
```

---

## Natural (Version) Sorting

```bash
ls -v
```

Sorts files naturally.

Example:

Without `-v`

```text
file1
file10
file2
```

With `-v`

```text
file1
file2
file10
```

---

## Combining Multiple Options

```bash
ls -Xvl
```

Equivalent to:

```bash
ls -X -v -l
```

Where:

- `-X` → Sort by extension
- `-v` → Natural sorting
- `-l` → Long listing format

---

# tree

The `tree` command displays directories in a tree-like structure.

---

## Display Directory Structure

```bash
tree
```

Example:

```text
project
├── src
├── docs
└── README.md
```

---

## Display Permissions

```bash
tree -p
```

Displays the directory tree along with file permissions.

Example:

```text
drwxr-xr-x project
├── drwxr-xr-x src
└── -rw-r--r-- README.md
```

---

# wc (Word Count)

The `wc` command displays statistics about files.

---

## Basic Usage

```bash
wc filename
```

Displays:

- Number of lines
- Number of words
- Number of bytes

Example:

```text
25 120 850 notes.txt
```

---

## Count Lines

```bash
wc -l filename
```

Displays only the number of lines.

---

## Count Words

```bash
wc -w filename
```

Displays only the number of words.

---

## Count Bytes

```bash
wc -c filename
```

Displays only the file size in bytes.

---

## Count Characters

```bash
wc -m filename
```

Displays the total number of characters.

---

## Display Longest Line Length

```bash
wc -L filename
```

Displays the length of the longest line in the file.

---

# Summary

In this topic, the following utilities were practiced:

- `ls` – List and sort files/directories.
- `tree` – Visualize directory structures.
- `wc` – Display file statistics such as lines, words, bytes, characters, and longest line length.

These commands are frequently used for file management, navigation, and system administration tasks in Linux.
