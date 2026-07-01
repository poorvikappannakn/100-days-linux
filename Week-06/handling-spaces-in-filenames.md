# Handling Files with Spaces in Linux

## Overview

Linux treats spaces as separators between command arguments. When a filename contains spaces, the filename must be enclosed in quotation marks or the spaces must be escaped.

---

## Creating a File

```bash
touch "client status.txt"
```

---

## Reading a File

```bash
cat "client status.txt"
```

---

## Editing a File

```bash
nano "client status.txt"
```

---

## Why Quotes Are Required

Without quotation marks:

```bash
cat client status.txt
```

Linux interprets this as two different files:

* client
* status.txt

With quotation marks:

```bash
cat "client status.txt"
```

Linux treats it as a single filename.

---

## Learning Outcome

* Work with filenames containing spaces.
* Understand command argument parsing.
* Access, edit and read files with spaces safely.
