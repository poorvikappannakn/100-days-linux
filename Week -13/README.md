# Week 13 – Progress

## 📅 Status

✅ Week 13 Completed

## 📖 Overview

This week focused on shell variables and basic Bash scripting concepts. The topics covered include creating and referencing variables, command substitution, arithmetic operations, environment variables, variable scope, handling whitespace when referencing variables, and handling command-line arguments.

---

## 📚 Topics Covered

### ✅ Shell Variables

* Creating shell variables using `=`
* Storing numeric values in variables
* Storing strings in variables
* Using variables with `echo`
* Making shell scripts executable
* Running shell scripts

---

### ✅ Referencing Shell Variables

* Referencing variables using `$`
* Escaping special characters using `\`
* Using `${}` to avoid ambiguity
* Preserving whitespace using quotes
* Understanding word splitting
* Difference between `echo $variable` and `echo "$variable"`

---

### ✅ Command Substitution

* Using `$()` for command substitution
* Capturing command output into variables
* Using command substitution with `date`
* Using command substitution with `ls`
* Using command substitution with `uptime`

---

### ✅ Arithmetic Operations

* Performing arithmetic using `$((expression))`
* Addition
* Subtraction
* Multiplication
* Division
* Modulus
* Increment
* Decrement

---

### ✅ Environment Variables

* Understanding environment variables
* Using common environment variables such as `$HOME`, `$LOGNAME`, `$SHELL`, and `$PATH`
* Creating environment variables using `export`
* Passing environment variables to child processes
* Removing variables using `unset`
* Understanding variable scope

---

### ✅ Command-Line Arguments

* Accessing command-line arguments using `$1`, `$2`, `$3`, etc.
* Using `$#` to determine the total number of arguments
* Using conditional statements to handle different numbers of arguments
* Using `elif` to check multiple conditions
* Using `-eq` to compare the number of arguments
* Understanding `fi` as the closing keyword of a Bash `if` statement
* Using `$@` to represent all command-line arguments
* Using a `for` loop to iterate through all arguments
* Using arithmetic expansion to maintain an argument counter
* Testing scripts with different numbers of command-line arguments

---

## 📂 Documentation Added

* `shell-variables.md`
* `command-line-arguments.md`

---

## 🧪 Practical Work

During this week, I practiced:

* Creating and using shell variables
* Working with environment variables
* Exporting variables
* Understanding variable inheritance
* Using command substitution
* Performing arithmetic operations
* Passing arguments to Bash scripts
* Processing multiple command-line arguments
* Using conditional statements
* Using loops with shell arguments
* Testing Bash scripts with different inputs

---

## 🚀 Key Learnings

- Shell variables store values that can be reused in commands and scripts.
- Variables can contain strings or numbers.
- `$variable` is used to reference a variable.
- `${variable}` can be used when clearer variable boundaries are required.
- Quoting variables helps preserve whitespace.
- `$()` performs command substitution.
- `$(( ))` performs arithmetic expansion.
- Environment variables can be passed to child processes.
- `export` makes a variable available to child processes.
- `$1`, `$2`, `$3`, etc. represent positional arguments.
- `$#` represents the number of arguments passed to a script.
- `$@` represents all positional arguments.
- `elif` allows multiple conditions to be checked.
- `fi` closes a Bash `if` statement.
- `for` loops can be used to process multiple command-line arguments.
- Bash scripting can automate repetitive command-line tasks.

---

## 📌 Week 13 Summary

Week 13 strengthened my understanding of Bash shell scripting fundamentals, especially variables, environment variables, command substitution, arithmetic operations, and command-line arguments.

The focus was on understanding how the shell handles data and how Bash scripts can accept and process input dynamically.

**Status: ✅ Completed**
