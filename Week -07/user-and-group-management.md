# User and Group Management

Linux groups make it easier to manage permissions for multiple users.

## Creating a Group

```bash
sudo groupadd groupname
```

Example:

```bash
sudo groupadd developers
```

---

## Adding a User to a Group

Using `usermod`:

```bash
sudo usermod -aG groupname username
```

Example:

```bash
sudo usermod -aG developers john
```

- `-a` appends the user to the group.
- `-G` specifies supplementary groups.

Without `-a`, existing supplementary groups may be replaced.

---

## Viewing Group Information

Linux stores group information in:

```text
/etc/group
```

To edit it:

```bash
sudo nano /etc/group
```

Editing this file requires root privileges.
