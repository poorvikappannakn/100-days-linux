# User Management

## Topics Covered

- Creating users
- Home directories
- Password management
- Modifying users
- Deleting users

## Commands Practiced

```bash
sudo useradd joker
sudo useradd -m bob
sudo passwd joker
sudo usermod -d /home/wayne joker
sudo usermod -m -d /home/joker joker
sudo usermod -s /bin/bash joker
sudo userdel -r bob
```

## Important Options

```text
-m = create home directory
-d = home directory
-s = login shell
-r = remove home directory
```

## Key Learnings

- Created Linux users.
- Assigned passwords.
- Modified user properties.
- Managed home directories.
- Deleted user accounts safely.
