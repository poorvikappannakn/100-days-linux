# Group Membership Management

## Removing a User from a Group

### Method 1 - Using gpasswd (Preferred)

```bash
sudo gpasswd -d username groupname
```

Example:

```bash
sudo gpasswd -d john developers
```

---

### Method 2 - Using usermod

```bash
sudo usermod -G group1,group2 username
```

Specify all the groups the user should remain a member of. Any omitted supplementary groups will be removed.

---

## Adding a User Using gpasswd

```bash
sudo gpasswd -a username groupname
```

Example:

```bash
sudo gpasswd -a john developers
```

---

## Notes

- Use `gpasswd` for simple group membership management.
- Use `usermod -aG` when adding users to supplementary groups.
- Be careful while editing `/etc/group`, as incorrect changes can affect user permissions.
