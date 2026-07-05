# Sort Command

## Overview

The `sort` command is used to arrange the lines of a text file in alphabetical or numerical order.

---

## Display Sorted Output

If you only want to view the sorted contents of a file, use:

```bash
sort filename
```

### Example

```bash
sort names.txt
```

This displays the sorted content on the terminal without modifying the original file.

---

## Save Sorted Output

If you want to save the sorted output into another file while keeping the original file unchanged, use the `-o` option.

```bash
sort input.txt -o output.txt
```

### Example

```bash
sort students.txt -o sorted_students.txt
```

The original file remains unchanged, and the sorted data is written to `sorted_students.txt`.

---

## Common Use Cases

* Sort names alphabetically.
* Arrange records before removing duplicates.
* Organize text files.
* Prepare files for further processing.

---

## Learning Outcome

* Sort file contents alphabetically.
* Save sorted output to a new file.
* Preserve the original file.
* Understand when to use the `-o` option.
