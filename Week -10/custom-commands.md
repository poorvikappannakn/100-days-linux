# Creating Custom Commands

## 📖 Introduction

Linux allows users to create their own executable commands using shell scripts.

---

# Why "Command Not Found" Occurs

Suppose a script named `hello` is created inside the home directory.

```text
~/hello
```

Running

```bash
hello
```

may produce

```text
command not found
```

This happens because Linux searches only the directories listed in the `PATH` variable.

---

## Running the Script

Execute it using its path.

```bash
~/hello
```

Or add its directory to the `PATH` environment variable.

---

# Creating a Custom Command

Example

```bash
cat > ~/hello <<EOF
#!/bin/bash

echo "Hello from TechCorp"
EOF
```

The `<<EOF` syntax reads everything until the ending `EOF`.

---

# Shebang

Example

```bash
#!/bin/bash
```

The shebang specifies which interpreter should execute the script.

In this example, the script will be executed using **Bash**.

---

# Key Commands

```bash
cat > ~/hello <<EOF

#!/bin/bash

echo "Hello from TechCorp"

EOF
```

```bash
~/hello
```

---

# Summary

- Linux searches only the directories present in `PATH`.
- Commands outside `PATH` must be executed using their path or added to `PATH`.
- Custom commands can be created using shell scripts.
- `<<EOF` is used to enter multiline content.
- `#!/bin/bash` tells Linux to execute the script using the Bash interpreter.
