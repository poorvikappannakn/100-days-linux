# Groups and User Accounts

## Topics Covered

- /etc/passwd
- /etc/shadow
- Groups
- Sudo access
- Locking and unlocking users

## Commands Practiced

```bash
sudo grep -w "joker" /etc/passwd
sudo cat /etc/shadow
sudo usermod -aG sudo joker
groups joker
su - joker
sudo passwd -l joker
sudo passwd -u joker
cat /etc/passwd
cut -d: -f1 /etc/passwd
grep "joker" /etc/passwd
```

## Important Files

### /etc/passwd

Stores:

- Username
- UID
- GID
- Home directory
- Login shell

### /etc/shadow

Stores encrypted password information.

## Key Learnings

- Understood Linux account storage.
- Learned the difference between passwd and shadow files.
- Added users to groups.
- Granted sudo privileges.
- Locked and unlocked user accounts.
