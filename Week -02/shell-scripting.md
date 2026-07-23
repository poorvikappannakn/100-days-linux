# Shell Scripting

## Topics Covered

- Shebang (#!)
- Single vs Double Quotes
- Creating a script
- Running a script

## Commands Practiced

```bash
echo '#!/bin/bash' > script.sh
echo 'echo "Hello World"' >> script.sh
chmod u+x script.sh
./script.sh
```

## Key Concepts

### Shebang

```bash
#!/bin/bash
```

Tells Linux to execute the script using Bash.

### Single Quotes

```bash
echo '$USER'
```

Displays text exactly as written.

### Double Quotes

```bash
echo "$USER"
```

Expands variables before displaying output.

## Key Learnings

- Learned how Bash scripts work.
- Understood the purpose of shebang.
- Practiced script execution.
- Learned quote handling in Bash.
