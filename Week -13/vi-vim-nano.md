# Vi, Vim and Nano Editors

## 📌 Overview

Linux provides terminal-based text editors for creating and editing files.

In this practice, I learned the basics of `vi`, `vim`, and `nano`, including editor modes, cursor movement, searching, deleting words, saving files, quitting, and the difference between Vi/Vim and Nano.

---

# Example 1 – Opening a File with Vi

### Command

```bash
vi filename
```

### Explanation

- `vi` is a text editor used in Linux.
- When Vi is opened, it starts in **Normal Mode**.
- Vi also provides **Insert Mode** for entering text.

---

# Example 2 – Vi Modes

Vi works mainly with different modes.

### Normal Mode

Normal Mode is used for commands such as:

- Cursor movement
- Searching
- Deleting text
- Saving the file
- Quitting the editor

### Insert Mode

Insert Mode is used to enter or edit text.

### Enter Insert Mode

```text
i
```

Pressing `i` enters Insert Mode.

### Return to Normal Mode

```text
Esc
```

Pressing `Esc` returns to Normal Mode.

---

# Example 3 – Saving and Quitting Vi

These commands are used from Normal Mode.

### Save the File

```text
:w
```

### Quit

```text
:q
```

### Save and Quit

```text
:wq
```

### Quit Without Saving

```text
:q!
```

### Explanation

- `:w` → saves/writes the file.
- `:q` → quits the editor.
- `:wq` → saves the file and quits.
- `:q!` → quits without saving changes.

---

# Example 4 – Basic Cursor Movement

The following keys can be used for cursor movement in Normal Mode.

### Commands

```text
h → move one character left
l → move one character right
j → move one line down
k → move one line up
```

### Move to the Beginning of the File

```text
gg
```

`gg` moves the cursor to the beginning of the file.

---

# Example 5 – Searching in Vi

The `/` command can be used to search for text.

### Command

```text
/a
```

Press `Enter` after entering the search pattern.

### Explanation

This searches for the next occurrence of `a` after the current cursor position.

### Find the Next Match

```text
n
```

`n` moves to the next matching occurrence.

---

# Example 6 – Deleting a Word

The `dw` command can be used to delete a word from the cursor position.

### Command

```text
dw
```

### Example

Suppose the cursor is at the beginning of:

```text
Now
```

Using:

```text
dw
```

deletes the word from the cursor position.

### Important Point

The cursor should be positioned appropriately before using `dw`.

---

# Example 7 – Using Vim

### Command

```bash
vim filename
```

### Explanation

Vim is an improved and enhanced version of Vi.

The basic concepts used with Vi also apply to Vim, including:

- Normal Mode
- Insert Mode
- Cursor movement
- Searching
- Deleting
- Saving
- Quitting

---

# Example 8 – Launching Vim Tutor

Vim provides an interactive tutorial for further practice.

### Command

```bash
vimtutor
```

### Explanation

`vimtutor` launches the interactive Vim tutorial, allowing Vim commands to be practiced directly.

---

# Example 9 – Opening a File with Nano

### Command

```bash
nano filename
```

### Explanation

`nano` is another terminal-based text editor.

The basic Nano editor was introduced as an alternative to Vi/Vim for editing files from the Linux terminal.

---

# Example 10 – Vi/Vim vs Nano

| Feature | Vi/Vim | Nano |
|---|---|---|
| Editing approach | Modal editing | Simpler editing interface |
| Normal Mode | Yes | No |
| Insert Mode | Yes | No separate Insert Mode |
| Cursor movement | Commands such as `h`, `j`, `k`, `l` | Direct cursor movement |
| Searching | `/pattern` | Search functionality |
| Deleting | Commands such as `dw` | Direct editing |
| Saving | `:w` | Editor shortcut |
| Quitting | `:q` | Editor shortcut |
| Learning curve | Higher | Easier for beginners |

### Main Difference

The main difference between Vi/Vim and Nano is their editing approach.

**Vi/Vim** uses a **modal editing system**. It separates commands and text entry into different modes.

For example:

```text
Normal Mode → commands
Insert Mode → entering text
```

**Nano** provides a simpler editing interface and does not use the same Normal Mode and Insert Mode workflow.

---

# Example 11 – Choosing Between Vi/Vim and Nano

### Using Vi/Vim

```bash
vim filename
```

Vi/Vim is useful when working with a command-based editing workflow and when practicing efficient terminal-based editing.

### Using Nano

```bash
nano filename
```

Nano is useful when a simpler terminal-based editor is preferred for editing a file.

---

# Example 12 – Basic Vi Workflow

A basic editing workflow can be represented as:

```text
Open file
   ↓
Normal Mode
   ↓
Press i
   ↓
Insert Mode
   ↓
Enter/Edit text
   ↓
Press Esc
   ↓
Normal Mode
   ↓
:wq
   ↓
Save and Quit
```

### Explanation

1. Open a file using `vi`.
2. Vi starts in Normal Mode.
3. Press `i` to enter Insert Mode.
4. Enter or modify the required text.
5. Press `Esc` to return to Normal Mode.
6. Use `:wq` to save the file and quit.

---

# 🚀 Key Learnings

- `vi` is a terminal-based text editor used in Linux.
- Vi works with different modes.
- Normal Mode is used for commands.
- Insert Mode is used for entering text.
- `i` enters Insert Mode.
- `Esc` returns to Normal Mode.
- `:w` saves the file.
- `:q` quits the editor.
- `:wq` saves the file and quits.
- `:q!` quits without saving.
- `h` moves the cursor left.
- `l` moves the cursor right.
- `j` moves the cursor down.
- `k` moves the cursor up.
- `gg` moves the cursor to the beginning of the file.
- `/` starts a search.
- `n` finds the next search match.
- `dw` deletes a word from the cursor position.
- Vim is an improved and enhanced version of Vi.
- `vimtutor` launches an interactive Vim tutorial.
- `nano filename` opens a file using Nano.
- Vi/Vim uses modal editing, while Nano provides a simpler editing interface.
