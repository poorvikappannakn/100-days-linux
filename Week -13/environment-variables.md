# Environment Variables

## 📌 Overview

Environment variables are variables that are available to processes running in the current shell environment.

They are commonly used to store system information and configuration values.

---

# Example 1 – Display Common Environment Variables

### Command

```bash
echo "Home directory: $HOME"
echo "Current user: $LOGNAME"
echo "Shell being used: $SHELL"
echo "Current PATH: $PATH"
```

### Example Output

```text
Home directory: /home/labex
Current user: labex
Shell being used: /bin/zsh
Current PATH: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

The actual values depend on the system.

### Explanation

- `$HOME` contains the user's home directory.
- `$LOGNAME` contains the current user's login name.
- `$SHELL` shows the shell being used.
- `$PATH` contains directories searched for executable commands.

---

# Example 2 – Create an Environment Variable

### Command

```bash
export MY_VARIABLE="Hello from my variable"
```

Display the variable:

```bash
echo "My new variable: $MY_VARIABLE"
```

### Output

```text
My new variable: Hello from my variable
```

### Explanation

`export` makes the variable available to child processes created from the current shell.

---

# Example 3 – Access an Environment Variable from a Child Process

### Script

```bash
export MY_VARIABLE="Hello from my variable"

bash -c 'echo "MY_VARIABLE in child process: $MY_VARIABLE"'
```

### Output

```text
MY_VARIABLE in child process: Hello from my variable
```

### Explanation

The child Bash process can access `MY_VARIABLE` because the variable was exported.

---

# Example 4 – Remove an Environment Variable

### Command

```bash
unset MY_VARIABLE
```

Verify:

```bash
echo "MY_VARIABLE after unsetting: $MY_VARIABLE"
```

### Output

```text
MY_VARIABLE after unsetting:
```

### Explanation

`unset` removes the variable from the current shell environment.

---

# Example 5 – Complete Environment Variable Script

```bash
#!/bin/bash

echo "Home directory: $HOME"
echo "Current user: $LOGNAME"
echo "Shell being used: $SHELL"
echo "Current PATH: $PATH"

export MY_VARIABLE="Hello from my variable"

echo "My new variable: $MY_VARIABLE"

bash -c 'echo "MY_VARIABLE in child process: $MY_VARIABLE"'

unset MY_VARIABLE

echo "MY_VARIABLE after unsetting: $MY_VARIABLE"
```

### Example Output

```text
Home directory: /home/labex
Current user: labex
Shell being used: /bin/zsh
Current PATH: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
My new variable: Hello from my variable
MY_VARIABLE in child process: Hello from my variable
MY_VARIABLE after unsetting:
```

---

# Common Environment Variables

| Variable | Purpose |
|---|---|
| `$HOME` | User's home directory |
| `$LOGNAME` | Current user's login name |
| `$SHELL` | Current shell |
| `$PATH` | Directories searched for commands |

---

# Practical Example – Passing Configuration to a Child Process

Suppose a script needs to tell a child process which environment it is running in.

```bash
export APP_ENV="development"

bash -c 'echo "Application environment: $APP_ENV"'
```

### Output

```text
Application environment: development
```

### Without `export`

If the variable is not exported:

```bash
APP_ENV="development"

bash -c 'echo "Application environment: $APP_ENV"'
```

The child process does not receive the variable, so the output will be:

```text
Application environment:
```

### Why This Is Useful

Environment variables can be used to pass configuration information from a parent shell to child processes without hard-coding the value inside every script.

---

# Environment Variable Commands

### Create / Export

```bash
export MY_VARIABLE="value"
```

### Display

```bash
echo "$MY_VARIABLE"
```

### Remove

```bash
unset MY_VARIABLE
```

---

# Practical Applications

- Configuring shell environments
- Passing values to child processes
- Storing system configuration
- Controlling command behavior
- Shell scripting
- Linux system administration

---

# Key Learnings

- Environment variables provide information and configuration to processes.
- `$HOME`, `$LOGNAME`, `$SHELL`, and `$PATH` are common environment variables.
- `export` makes a variable available to child processes.
- `unset` removes a variable.
- Child processes can access exported variables.
