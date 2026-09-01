# Standard Input and Output Redirection

## Topics Covered

- Standard output
- Standard error
- Redirecting standard output using `>`
- Redirecting standard error using `2>`
- Appending standard error using `2>>`
- Using `tee`
- Appending output with `tee -a`
- Redirecting standard input using `<`

## Commands Practiced

```bash
ls /etc/ > output.txt

ls /etc/nonexistent 2> error.log

ls /etc/nonexistent 2>> error.log

ls /etc | tee output.txt

ls /etc | tee -a output.txt

sort < fruit.txt
```

## Examples

### Redirecting Standard Output

The `>` operator redirects standard output to a file.

```bash
ls /etc/ > output.txt
```

Instead of displaying the output only on the terminal, the output is written to `output.txt`.

The file can then be viewed using:

```bash
cat output.txt
```

---

### Redirecting Standard Error

The `2>` operator redirects standard error to a file.

For example, if a file does not exist:

```bash
ls /etc/nonexistent 2> error.log
```

The error message is redirected to `error.log` instead of being displayed on the terminal.

The error can then be viewed using:

```bash
cat error.log
```

A useful distinction is:

```text
1 → Standard Output
2 → Standard Error
```

---

### Appending Standard Error

The `2>>` operator appends standard error to a file instead of replacing its existing contents.

```bash
ls /etc/nonexistent 2>> error.log
```

This is useful when multiple errors need to be recorded in the same file.

---

### Using `tee`

`tee` is used when the output should be displayed on the screen and also written to a file.

```bash
ls /etc | tee output.txt
```

The output is displayed in the terminal and also stored in `output.txt`.

---

### Appending with `tee -a`

The `-a` option makes `tee` append to the file instead of overwriting it.

```bash
ls /etc | tee -a output.txt
```

This preserves the existing contents of `output.txt` and adds the new output to the end.

---

### Redirecting Standard Input

The `<` operator redirects standard input from a file.

First, create a file containing values:

```bash
echo "banana" >> fruit.txt
echo "apple" >> fruit.txt
echo "cherry" >> fruit.txt
```

The file contains:

```text
banana
apple
cherry
```

Now use:

```bash
sort < fruit.txt
```

Output:

```text
apple
banana
cherry
```

### Explanation

The `<` operator tells `sort` to take its input from `fruit.txt`.

The `sort` command then reads the contents of the file and sorts them.

---

## Key Learnings

- Standard output is normally associated with file descriptor `1`.
- Standard error is associated with file descriptor `2`.
- `>` redirects standard output to a file.
- `2>` redirects standard error to a file.
- `2>>` appends standard error to a file.
- `tee` displays output on the terminal and also writes it to a file.
- `tee -a` appends output to a file.
- `<` redirects standard input from a file.
- Redirection allows command input and output to be controlled using files.
