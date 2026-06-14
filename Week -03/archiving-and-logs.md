# Archiving and Log Management

## Commands Practiced

```bash
mkdir -p project/investigation/dir1/dir2/dir3

ls -F

cp config.json config.json.bak

tar -czf archive.tar.gz file1 file2

tar -tf archive.tar.gz
```

---

## mkdir -p

```bash
mkdir -p project/investigation/dir1/dir2/dir3
```

Flag:

```text
-p = create parent directories if needed
```

---

## ls -F

```bash
ls -F
```

Displays file types.

Directories end with:

```text
/
```

---

## Backup Files

```bash
cp config.json config.json.bak
```

Convention:

```text
.bak = backup file
```

---

## tar

Create compressed archive:

```bash
tar -czf archive.tar.gz file1 file2
```

Flag meanings:

```text
c = create archive

z = compress using gzip

f = archive filename follows
```

---

## Archive Log Files

```bash
tar -czf old-logs.tar.gz *2023*.log
```

Creates an archive containing matching 2023 log files.

---

## View Archive Contents

```bash
tar -tf old-logs.tar.gz
```

Flag meanings:

```text
t = list archive contents

f = archive filename
```

---

## Key Learnings

- Created nested directories.
- Backed up configuration files.
- Created compressed archives.
- Managed log files using tar.
