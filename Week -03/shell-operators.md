# Shell Operators and Redirection

## Output Redirection

Store output in a file:

```bash
whoami > system.txt
```

---

## Multiple Commands

```bash
whoami ; uname -a ; uptime
```

Runs commands sequentially.

---

## Store Multiple Outputs

```bash
(whoami ; uname -a ; uptime) > system.txt
```

Stores combined output inside system.txt.

---

## Key Learnings

- Redirected command output to files.
- Combined multiple commands.
- Generated simple system reports.
