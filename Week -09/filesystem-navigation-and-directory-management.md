# Filesystem Navigation & Directory Management

## pwd (Print Working Directory)

The `pwd` command displays the path of the current working directory.

### Print the Logical Path

```bash
pwd -L
```

Displays the logical path, preserving symbolic links.

### Print the Physical Path

```bash
pwd -P
```

Resolves symbolic links and displays the actual physical path.

---

## cd (Change Directory)

The `cd` command is used to navigate between directories.

### Go Back to the Previous Directory

```bash
cd -
```

Switches back to the previously visited directory.

> Useful when frequently switching between two directories.

### Go to the Root Directory

```bash
cd /
```

Navigates to the root directory of the Linux filesystem.

---

# mkdir (Make Directory)

The `mkdir` command creates one or more directories.

---

## Create a Directory with Custom Permissions

```bash
mkdir -m 700 directory_name
```

Creates a directory with permission mode **700**.

### Permission Breakdown

| Permission | Meaning |
|------------|---------|
| 7 | Read + Write + Execute |
| 0 | No permissions |
| 0 | No permissions |

Result:

- Owner → Read, Write, Execute
- Group → No permissions
- Others → No permissions

---

## Verbose Mode

```bash
mkdir -v dir1 dir2 dir3
```

Displays a message for every directory created.

Example Output:

```text
mkdir: created directory 'dir1'
mkdir: created directory 'dir2'
mkdir: created directory 'dir3'
```

Useful when creating multiple directories and verifying that each directory is created successfully.

---

## Create Parent Directories

```bash
mkdir -p parent/child/grandchild
```

Creates all missing parent directories automatically.

---

## Combining Multiple Options

```bash
mkdir -pvm 750 project/src
```

Equivalent to:

```bash
mkdir -p -v -m 750 project/src
```

Where:

- `-p` → Create parent directories
- `-v` → Verbose output
- `-m 750` → Set directory permissions

### Note

When combining options, it is preferable to place the option that requires a value (`-m`) at the end for better readability.

Example:

```bash
mkdir -pvm 750 project
```

instead of

```bash
mkdir -pmv750 project
```

---

## Listing Newly Created Directories

```bash
ls -lR ./
```

Displays the created directory structure recursively along with permissions.
