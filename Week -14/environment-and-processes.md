# Environment Variables and Processes

## Topics Covered

- Local variables
- Environment variables
- Variable inheritance
- Child shells
- Process ID (PID)
- Parent Process ID (PPID)
- Returning to the parent shell

## Commands Practiced

```bash
flower=rose
echo $flower

env
env | grep flower

export nut=almond
env | grep nut

echo $$
bash
zsh
ps -f
exit
```

## Examples

### Local Variable

```bash
flower=rose
echo $flower
```

Output:

```text
rose
```

A local variable is available in the current shell.

### Checking Environment Variables

```bash
env
```

`env` displays environment variables.

```bash
env | grep flower
```

If `flower` was created only as a local variable, it will not appear in the environment.

### Exporting a Variable

```bash
export nut=almond
```

Check it:

```bash
env | grep nut
```

Output:

```text
nut=almond
```

`export` makes the variable available to child processes.

### Child Shell

```bash
bash
```

or:

```bash
zsh
```

These commands start a child shell.

An exported environment variable can be inherited by the child shell.

### Process ID

```bash
echo $$
```

`$$` gives the Process ID (PID) of the current shell.

### Viewing Processes

```bash
ps -f
```

Important fields:

- `PID` → Process ID
- `PPID` → Parent Process ID

### Returning to the Parent Shell

```bash
exit
```

`exit` closes the current child shell and returns to the parent shell.

## Key Learnings

- Learned the difference between local and environment variables.
- Learned how `export` allows variables to be inherited by child processes.
- Practiced creating child shells using `bash` and `zsh`.
- Learned how to check the current shell's PID using `$$`.
- Learned the meaning of PID and PPID.
- Practiced returning to the parent shell using `exit`.
