# Text Processing with cut

## Delimiters

A delimiter is a character used to separate fields in a line of text.

Example:

```text
maya:analyst:finance:active
```

Here, the colon (`:`) is the delimiter.

Fields:

| Field | Value |
|------|-------|
| 1 | maya |
| 2 | analyst |
| 3 | finance |
| 4 | active |

---

## The `cut` Command

The `cut` command extracts specific fields from a file or command output.

### Syntax

```bash
cut -d "delimiter" -f field_number filename
```

### Example

```bash
cut -d ":" -f1 access
```

Output:

```text
maya
```

Explanation:

- `-d ":"` specifies the delimiter.
- `-f1` selects the first field.

This command extracts only the first field from each line of the file.
