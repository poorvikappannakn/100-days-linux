# Hard Links, Symbolic Links and Inodes

## Topics Covered

- Creating links
- Symbolic links
- Hard links
- Inodes
- Comparing files using inode numbers
- Understanding how links refer to file data
- Effect of deleting a linked file

## Commands Practiced

```bash
ln -s <source> <destination>

ls -li fileA
```

## Examples

### Creating a Symbolic Link

### Command

```bash
ln -s <source> <destination>
```

The `-s` option creates a symbolic link.

A symbolic link stores a path to another file or directory.

---

### Example of a Symbolic Link

Suppose the original file is:

```text
fileA
```

Create a symbolic link:

```bash
ln -s fileA fileC
```

Here:

```text
fileA → original file
fileC → symbolic link to fileA
```

The symbolic link points to the original file rather than being another directory entry referring directly to the same inode.

---

### Checking Inode Numbers

The `-i` option of `ls` displays inode numbers.

```bash
ls -li fileA
```

Example output:

```text
21113 -rw-r--r-- 1 user user 2 Aug 31 fileA
```

The number at the beginning is the inode number.

An inode is a unique identifier for a file within a filesystem and contains metadata associated with the file.

---

### Hard Links

A hard link is another directory entry referring to the same file data and inode.

For example, if two filenames refer to the same inode, they refer to the same underlying file data.

This can be observed using:

```bash
ls -li fileA fileB
```

Example:

```text
21113 -rw-r--r-- 2 user user 2 Aug 31 fileA
21113 -rw-r--r-- 2 user user 2 Aug 31 fileB
```

Both files have the same inode number:

```text
fileA → inode 21113
fileB → inode 21113
```

The link count is also shown in the output.

---

### Comparing Hard Links and Symbolic Links

```text
Hard Link
    ↓
Same inode
    ↓
Same underlying file data

Symbolic Link
    ↓
Points to another file path
    ↓
Different inode
```

---

### What Happens When One Hard Link Is Deleted?

Suppose:

```text
fileA → same inode
fileB → same inode
```

If `fileA` is deleted, `fileB` still refers to the same underlying file data.

The data is still accessible through `fileB`.

---

### What Happens When the Target of a Symbolic Link Is Deleted?

If:

```text
fileA → original file
fileC → symbolic link to fileA
```

and `fileA` is deleted, `fileC` can become a broken symbolic link because the path it points to no longer exists.

If a new file is later created with the same name, the symbolic link can point to that new file because it stores the path rather than the original file's inode.

---

## Key Learnings

- `ln -s` creates a symbolic link.
- A symbolic link stores a path to another file or directory.
- An inode identifies a file within a filesystem.
- `ls -i` displays inode numbers.
- Hard links refer directly to the same inode and underlying file data.
- Multiple hard links can refer to the same file data.
- Deleting one hard link does not immediately delete the underlying data if another hard link still exists.
- A symbolic link has its own inode and points to another path.
- A symbolic link can become broken when its target is removed.
