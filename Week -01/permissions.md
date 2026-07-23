# Linux Permissions

## Permission Types

```text id="d1w7m4"
r = read
w = write
x = execute
```

---

## Permission Groups

```text id="u4m8q2"
u = user
g = group
o = others
```

---

## Commands Practiced

```bash id="kmywe9"
chmod
ls -l
```

---

## Symbolic Permission Example

```bash id="pv4z8x"
chmod u+x script.sh
```

Adds execute permission for user.

---

## Numeric Permission Example

```bash id="a2n7m5"
chmod 700 file.txt
```

Meaning:

* owner has full permission
* group has no permission
* others have no permission

---

## Key Learnings

* Linux permissions control access to files and directories
* `ls -l` displays permission details
* `chmod` modifies permissions
* Permissions are important for system security
