# Week 13 – Progress

## 📅 Status

🚧 Week 13 is currently in progress.

## 📖 Overview

This week focuses on shell variables and basic Bash scripting concepts, including creating and referencing variables, command substitution, arithmetic operations, environment variables, variable scope, handling whitespace when referencing variables, handling command-line arguments, working with shell arrays, and basic Linux text editors and shell processes.

---

## 📚 Topics Covered So Far

### ✅ Shell Variables

* Creating shell variables using `=`
* Storing numeric values in variables
* Storing strings in variables
* Using variables with `echo`
* Making shell scripts executable
* Running shell scripts

### ✅ Referencing Shell Variables

* Referencing variables using `$`
* Escaping special characters using `\`
* Using `${}` to avoid ambiguity
* Preserving whitespace using quotes
* Understanding word splitting
* Difference between `echo $variable` and `echo "$variable"`

### ✅ Command Substitution

* Using `$()` for command substitution
* Capturing command output into variables
* Using command substitution with `date`
* Using command substitution with `ls`
* Using command substitution with `uptime`

### ✅ Arithmetic Operations

* Performing arithmetic using `$((expression))`
* Addition
* Subtraction
* Multiplication
* Division
* Modulus
* Increment
* Decrement

### ✅ Environment Variables

* Understanding environment variables
* Using common environment variables such as `$HOME`, `$LOGNAME`, `$SHELL`, and `$PATH`
* Creating environment variables using `export`
* Passing environment variables to child processes
* Removing variables using `unset`
* Understanding variable scope
* Testing whether a variable is available as an environment variable
* Observing environment variables using `env`

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

### ✅ Shell Arrays

* Creating arrays in Bash
* Storing multiple elements in an array
* Understanding array indexing
* Accessing individual array elements
* Finding the number of elements in an array using `${#array[@]}`
* Adding elements to an array using `+=`
* Working with different types of array values such as numbers and strings

### ✅ Vi and Vim

* Understanding `vi` as a text editor used in Linux
* Understanding Normal Mode and Insert Mode
* Entering Insert Mode using `i`
* Returning to Normal Mode using `Esc`
* Saving a file using `:w`
* Quitting using `:q`
* Saving and quitting using `:wq`
* Quitting without saving using `:q!`
* Understanding Vim as an improved version of Vi
* Launching the interactive Vim tutorial using `vimtutor`
* Moving the cursor using `h`, `j`, `k`, and `l`
* Moving to the beginning of a file using `gg`
* Searching for a character using `/`
* Moving to the next search result using `n`
* Deleting a word using `dw`

### ✅ Nano

* Introduction to the Nano text editor
* Opening a file using `nano filename`

### ✅ Local and Environment Variables

* Understanding the difference between local variables and environment variables
* Creating a local variable
* Checking a local variable using `echo`
* Understanding that local variables are available within the current shell
* Creating environment variables using `export`
* Checking exported variables using `env`
* Understanding that environment variables can be inherited by child processes

### ✅ Shell Processes and Child Shells

* Understanding the relationship between a parent shell and a child shell
* Starting a child shell using `bash`
* Observing the current process ID using `$$`
* Using `ps -f` to view process information
* Understanding `PPID` as the parent process ID
* Using `exit` to return from a child shell to the parent shell
* Observing variable inheritance between parent and child shells

---

## 📂 Documentation Added

* `shell-variables.md`
* `command-line-arguments.md`
* `shell_arrays.md`

---

## 🚀 Progress

Week 13 is still ongoing. More shell scripting concepts, Linux text-editor usage, shell processes, and practical exercises will be added before the week is completed.
