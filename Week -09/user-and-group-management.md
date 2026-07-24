# User and Group Management

## passwd

The `passwd` command is used to manage user passwords.

### Syntax

```bash
passwd
```

Changes your own password.

---

```bash
sudo passwd username
```

Changes another user's password.

---

```bash
sudo passwd -l username
```

Locks a user account by disabling password authentication.

---

```bash
sudo passwd -u username
```

Unlocks a previously locked user account.

---

```bash
sudo passwd -d username
```

Deletes the user's password.

---

### Password Storage

User password hashes are stored securely in:

```text
/etc/shadow
```

The `passwd` command safely updates this file.

---

# gpasswd

The `gpasswd` command is used for group administration.

---

## Add a User to a Group

```bash
sudo gpasswd -a user group
```

Adds the specified user to the group.

---

## Remove a User from a Group

```bash
sudo gpasswd -d user group
```

Removes the specified user from the group.

---

## Set a Group Password

```bash
sudo gpasswd group
```

Sets a password for the specified group.

---

## Remove a Group Password

```bash
sudo gpasswd -r group
```

Removes the group's password.

---

## Assign Group Administrator

```bash
sudo gpasswd -A user group
```

Assigns the specified user as the group administrator.
