# Password Management

Linux supports two types of password management:

1. User passwords
2. Group passwords

---

## User Password Management (`passwd`)

The `passwd` command is used to manage user account passwords.

### Change your own password

```bash
passwd
```

### Change another user's password

```bash
sudo passwd username
```

### Lock a user account

```bash
sudo passwd -l username
```

### Unlock a user account

```bash
sudo passwd -u username
```

### Delete a user's password

```bash
sudo passwd -d username
```

User password hashes are stored in:

```text
/etc/shadow
```

---

## Group Password Management (`gpasswd`)

The `gpasswd` command is used to manage Linux groups.

### Add a user to a group

```bash
sudo gpasswd -a username groupname
```

### Remove a user from a group

```bash
sudo gpasswd -d username groupname
```

### Set a group password

```bash
sudo gpasswd groupname
```

### Remove a group password

```bash
sudo gpasswd -r groupname
```

### Assign a group administrator

```bash
sudo gpasswd -A username groupname
```

---

## Summary

- `passwd` manages user passwords.
- `gpasswd` manages group membership, administrators, and group passwords.
