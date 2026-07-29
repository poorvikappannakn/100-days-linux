# Command Location and PATH

## 📖 Introduction

Linux uses the **PATH** environment variable to locate executable commands. The `which` command helps identify the exact executable that will run when a command is entered.

---

# The `which` Command

The `which` command displays the location of an executable command.

### Syntax

```bash
which <command_name>
```

### Example

```bash
which python
```

**Output**

```text
/usr/local/bin/python
```

---

## Why use `which`?

- Verify whether a program is installed.
- Find the executable location.
- Troubleshoot which executable is currently being used.

Example:

```bash
which gcc
```

If installed:

```text
/usr/bin/gcc
```

Otherwise:

```text
gcc not found
```

---

# Multiple Executables

A system can contain multiple versions of the same executable.

Example:

```text
/usr/local/bin/python
/usr/bin/python
/opt/python
```

Display all matching executables:

```bash
which -a python
```

Example Output

```text
/usr/local/bin/python
/usr/bin/python
/opt/python
```

> **Note:** `which` displays only the first match, while `which -a` displays every matching executable.

---

# Understanding PATH

`PATH` is an environment variable that stores the directories Linux searches for executable commands.

Think of it as a list of folders searched from left to right.

---

## View PATH

```bash
echo $PATH
```

Example

```text
/usr/local/bin:/usr/bin:/bin
```

- `:` separates directories.
- Linux searches directories from left to right.

---

# PATH Priority

Suppose PATH contains:

```text
A:B:C:D
```

Linux searches in the following order:

```
A → B → C → D
```

As soon as the executable is found, the search stops.

---

# Updating PATH

### Add a directory to the beginning

```bash
export PATH=$HOME/custom-bin:$PATH
```

Linux searches this directory first.

---

### Add a directory to the end

```bash
export PATH=$PATH:$HOME/custom-bin
```

Linux searches this directory last.

---

# Using Variables

Use `$` when reading a variable.

Examples

```bash
echo $PATH
```

```bash
echo $HOME
```

Do **not** use `$` while creating or updating a variable.

Example

```bash
name="Poorvik"
```

Display its value:

```bash
echo $name
```

Update PATH:

```bash
export PATH=$PATH:$HOME/bin
```

---

# Key Commands

```bash
which python
which -a python

echo $PATH
echo $HOME

export PATH=$HOME/custom-bin:$PATH
export PATH=$PATH:$HOME/custom-bin
```

---

# Summary

- `which` finds the executable location.
- `which -a` lists all matching executables.
- `PATH` stores directories searched for commands.
- Linux searches PATH from left to right.
- The first matching executable is executed.
- Use `$` when reading variables.
- Do not use `$` while assigning variables.
- `export PATH` updates the command search path.
