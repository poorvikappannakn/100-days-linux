# Shell Options and Configuration

## Topics Covered

- Shell options
- `set -o`
- `allexport`
- `SHELLOPTS`
- `.bashrc`
- `.zshrc`
- `source`
- Persisting shell options

## Commands Practiced

```bash
set -o
set -o | grep allexport

set -o allexport
set +o allexport

set -o
set -o name
set +o name

echo $SHELLOPTS

source ~/.bashrc
source ~/.zshrc
```

## Examples

### Viewing Shell Options

```bash
set -o
```

Displays shell options and their current states.

To check a specific option:

```bash
set -o | grep allexport
```

### Enabling `allexport`

```bash
set -o allexport
```

`allexport` causes newly created shell variables to be automatically exported.

### Disabling `allexport`

```bash
set +o allexport
```

This disables the `allexport` option.

### Enabling and Disabling Shell Options

Enable an option:

```bash
set -o name
```

Disable an option:

```bash
set +o name
```

### Checking `SHELLOPTS`

```bash
echo $SHELLOPTS
```

`SHELLOPTS` provides information about the shell options enabled in the current shell.

### Bash Configuration

The Bash configuration file is:

```text
~/.bashrc
```

A shell option can be added to `.bashrc`, for example:

```bash
set -o allexport
```

Reload the configuration:

```bash
source ~/.bashrc
```

### Zsh Configuration

The Zsh configuration file is:

```text
~/.zshrc
```

A shell option can be added to `.zshrc`:

```bash
set -o allexport
```

Reload it using:

```bash
source ~/.zshrc
```

### Persisting a Shell Option

Basic workflow:

```text
Open ~/.bashrc or ~/.zshrc
        ↓
Add the required shell option
        ↓
Save the file
        ↓
source the configuration file
        ↓
The configuration is loaded
```

For Bash:

```bash
nano ~/.bashrc
source ~/.bashrc
```

For Zsh:

```bash
nano ~/.zshrc
source ~/.zshrc
```

## Key Learnings

- Learned that shell options control shell behavior.
- Practiced viewing shell options using `set -o`.
- Learned how to enable and disable options.
- Learned about the `allexport` option.
- Learned how `SHELLOPTS` provides information about shell options.
- Learned the purpose of `.bashrc` and `.zshrc`.
- Practiced reloading shell configuration using `source`.
- Learned how shell options can be made persistent through configuration files.
