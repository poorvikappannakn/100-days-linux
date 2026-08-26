# Shell Aliases

## Topics Covered

- Creating aliases
- Using aliases as command shortcuts
- Verifying aliases
- Removing aliases

## Commands Practiced

```bash
alias ldetc='ls -ld /etc'
alias ldetc
ldetc
unalias ldetc
```

## Examples

### Creating an Alias

```bash
alias ldetc='ls -ld /etc'
```

This creates `ldetc` as a shortcut for:

```bash
ls -ld /etc
```

### Using the Alias

```bash
ldetc
```

The alias executes the command:

```bash
ls -ld /etc
```

### Checking an Alias

```bash
alias ldetc
```

This displays the command associated with the alias.

### Removing an Alias

```bash
unalias ldetc
```

This removes the `ldetc` alias from the current shell.

After removal, `ldetc` is no longer available as that shortcut.

## Key Learnings

- Learned that aliases provide shortcuts for frequently used commands.
- Practiced creating an alias using `alias`.
- Learned how to check an existing alias.
- Practiced removing an alias using `unalias`.
