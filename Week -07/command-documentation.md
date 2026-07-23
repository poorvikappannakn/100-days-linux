# Command Documentation

## Built-in vs External Commands

Linux commands are either built into the shell or stored as executable files in the filesystem.

### Checking the Command Type

The `type` command identifies whether a command is built-in or external.

```bash
type cd
type ls
```

Example:

```text
cd is a shell builtin
ls is /usr/bin/ls
```

- `cd` is a shell built-in command.
- `ls` is an external command.

---

## Using Manual Pages

The `man` command displays the manual page for a command.

```bash
man <command>
```

Example:

```bash
man ls
```

### Navigation

| Key | Action |
|------|--------|
| ↑ / ↓ | Scroll line by line |
| Space | Next page |
| b | Previous page |
| / | Search for a keyword |
| n | Next search result |
| q | Quit |

---

## Searching Documentation

The `apropos` command searches manual page descriptions using a keyword.

```bash
apropos password
apropos file
```

This is useful when you know what you want to do but don't remember the exact command.
