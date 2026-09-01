# User Switching and User Management

## Topics Covered

- Switching users with `su`
- Difference between `su username` and `su - username`
- Password aging information
- `chage`
- User group management
- Creating groups
- Adding users to groups
- Modifying secondary group membership
- Deleting users
- Deleting a user's home directory

## Commands Practiced

```bash
su username

su - username

sudo chage -l student1

sudo chage -M 90 -m 7 -W 14 student1

sudo groupadd groupname

sudo usermod -aG groupname username

sudo usermod -G groupname username

sudo userdel user-name

sudo userdel -r user-name
```

## Examples

### Switching Users with `su`

```bash
su username
```

`su username` switches to another user while keeping much of the current shell environment.

---

### Switching Users with a Login Shell

```bash
su - username
```

`su - username` switches to the specified user and starts a login shell for that user.

The `-` makes the new shell behave more like a fresh login session.

### Difference

```text
su username
    ↓
Switch user
    ↓
Keep much of the current shell environment

su - username
    ↓
Switch user
    ↓
Start a login shell for that user
```

---

### Checking Password Aging Information

```bash
sudo chage -l student1
```

This displays password aging information for the user.

Typical information includes:

```text
Last password change
Password expires
Password inactive
Account expires
Minimum number of days between password change
Maximum number of days between password change
Number of days of warning before password expires
```

---

### Setting Password Aging Rules

```bash
sudo chage -M 90 -m 7 -W 14 student1
```

This sets password aging values for `student1`.

The options represent:

- `-M 90` → maximum number of days before the password must be changed
- `-m 7` → minimum number of days between password changes
- `-W 14` → number of warning days before password expiration

The settings can be checked again using:

```bash
sudo chage -l student1
```

---

### Creating a Group

```bash
sudo groupadd groupname
```

This creates a new group.

---

### Adding a User to a Secondary Group

```bash
sudo usermod -aG groupname username
```

The options mean:

- `-G` → specify supplementary/secondary groups
- `-a` → append the group instead of replacing the user's existing supplementary groups

---

### Replacing Secondary Group Membership

```bash
sudo usermod -G groupname username
```

Using `-G` without `-a` replaces the user's existing supplementary group list with the groups specified by the command.

Therefore, `-aG` is important when the intention is to add a user to another group without removing existing secondary groups.

---

### Deleting a User

```bash
sudo userdel user-name
```

This removes the user account.

---

### Deleting a User and Home Directory

```bash
sudo userdel -r user-name
```

The `-r` option removes the user's home directory and associated mail spool along with the user account.

---

### Locked Password Information

When a user's password is locked, the password entry in `/etc/shadow` can contain exclamation marks such as:

```text
!!
```

or:

```text
!
```

The `!` invalidates the stored password hash for password authentication.

This prevents the stored password hash from being matched as a normal password.

---

## Key Learnings

- `su username` switches to another user while retaining much of the current shell environment.
- `su - username` starts a login shell for the target user.
- `chage -l` displays password aging information.
- `chage` can configure password expiration and warning policies.
- `-M` sets the maximum password age.
- `-m` sets the minimum password age.
- `-W` sets the warning period before password expiration.
- `groupadd` creates a new group.
- `usermod -aG` adds a user to a secondary group without replacing existing secondary groups.
- `usermod -G` changes the user's supplementary group list.
- `userdel` removes a user account.
- `userdel -r` also removes the user's home directory.
- Password locking can be represented by `!` in the password field of `/etc/shadow`.
