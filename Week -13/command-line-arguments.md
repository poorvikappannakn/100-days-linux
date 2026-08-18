# Command-Line Arguments in Bash

## 📌 Overview

Command-line arguments allow a Bash script to receive values when the script is executed.

In this lab, I learned how to:

* Access individual arguments using `$1`, `$2`, `$3`, etc.
* Use `$#` to find the total number of arguments.
* Use conditional statements to handle different numbers of arguments.
* Use `$@` to loop through all provided arguments.
* Use arithmetic expansion to maintain an argument counter.

---

# Example 1 – Handle the Number of Arguments

### Command

```bash
#!/bin/bash

if [ $# -eq 0 ]; then
  echo "No arguments provided."
elif [ $# -eq 1 ]; then
  echo "One argument provided: $1"
elif [ $# -eq 2 ]; then
  echo "Two arguments provided: $1 and $2"
else
  echo "More than two arguments provided:"
  echo "First argument: $1"
  echo "Second argument: $2"
  echo "Third argument: $3"
  echo "Total number of arguments: $#"
fi
```

### Explanation

* `$#` is a special variable that contains the number of arguments passed to the script.
* `[ $# -eq 0 ]` checks whether the number of arguments is equal to `0`.
* `elif` means "else if" and allows multiple conditions to be checked.
* `-eq` means "equal to".
* `$1`, `$2`, and `$3` represent the first, second, and third arguments.
* `fi` closes the Bash `if` statement.

### Understanding `fi`

`fi` ends a Bash `if` statement. It is `if` written backward.

```bash
if [ $# -eq 0 ]; then
  echo "No arguments provided."
fi
```

Here:

* `if` starts the conditional statement.
* `[ $# -eq 0 ]` checks the condition.
* `then` starts the commands executed when the condition is true.
* `fi` closes the `if` statement.

---

# Example 2 – Test Different Argument Counts

### Command

```bash
./arguments.sh
./arguments.sh one
./arguments.sh one two
./arguments.sh one two three four
```

### Output

```text
No arguments provided.

One argument provided: one

Two arguments provided: one and two

More than two arguments provided:
First argument: one
Second argument: two
Third argument: three
Total number of arguments: 4
```

### Explanation

The script changes its behavior depending on how many arguments are supplied.

* `./arguments.sh` provides zero arguments.
* `./arguments.sh one` provides one argument.
* `./arguments.sh one two` provides two arguments.
* `./arguments.sh one two three four` provides more than two arguments.

This demonstrates how `$#` can be used to make a script handle different numbers of command-line arguments.

---

# Example 3 – Loop Through All Arguments

### Command

```bash
#!/bin/bash

echo "Total number of arguments: $#"
echo "All arguments:"

count=1
for arg in "$@"; do
  echo "Argument $count: $arg"
  count=$((count + 1))
done
```

### Explanation

* `$@` represents all the arguments passed to the script.
* The `for` loop iterates through the provided arguments.
* `arg` stores the current argument during each iteration.
* `count=1` initializes the argument counter.
* `$((count + 1))` is arithmetic expansion used to increase the counter by `1`.
* `"$@"` allows the script to process all provided arguments.

---

# Example 4 – Test the Final Script

### Command

```bash
./arguments.sh apple banana cherry date
```

### Output

```text
Total number of arguments: 4
All arguments:
Argument 1: apple
Argument 2: banana
Argument 3: cherry
Argument 4: date
```

### Explanation

The script receives four arguments:

1. `apple`
2. `banana`
3. `cherry`
4. `date`

`$#` reports that there are `4` arguments, while `$@` allows the `for` loop to process each argument individually.

---

# 📌 Key Special Variables

| Variable | Meaning                    |
| -------- | -------------------------- |
| `$1`     | First argument             |
| `$2`     | Second argument            |
| `$3`     | Third argument             |
| `$#`     | Total number of arguments  |
| `$@`     | All command-line arguments |

---

# 🚀 Key Learnings

* Bash scripts can accept values from the command line.
* `$1`, `$2`, `$3`, etc. are used to access individual arguments.
* `$#` determines how many arguments were provided.
* Conditional statements can handle different argument counts.
* `$@` can be used to process all arguments.
* A `for` loop can iterate through every argument.
* Arithmetic expansion can be used to maintain a counter.
* Command-line arguments make scripts more flexible because the same script can process different input values.
