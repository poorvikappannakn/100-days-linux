# Shell Basics

## 📌 Overview

Shell variables are used to store values that can be used later in a Bash script.

Variables can store numbers, strings, and other information required by a shell script.

---

# Example 1 – Create Shell Variables

### Script

```bash
#!/bin/bash

PRICE_PER_APPLE=5
MyFirstLetters=ABC
greeting='Hello        world!'

echo "Price per apple: $PRICE_PER_APPLE"
echo "My first letters: $MyFirstLetters"
echo "Greeting: $greeting"
```

### Explanation

- `PRICE_PER_APPLE=5` creates a variable containing a number.
- `MyFirstLetters=ABC` creates a string variable.
- `greeting='Hello        world!'` stores a string containing multiple spaces.
- Variables are assigned using `=` without spaces around it.

### Output

```text
Price per apple: 5
My first letters: ABC
Greeting: Hello        world!
```

---

# Example 2 – Make a Script Executable

### Command

```bash
chmod +x /home/labex/project/variables.sh
```

Run the script:

```bash
./variables.sh
```

### Explanation

`chmod +x` gives the script execute permission.

---

# Referencing Shell Variables

Variables are referenced using `$` followed by the variable name.

```bash
echo "$PRICE_PER_APPLE"
```

---

# Example 3 – Escaping Special Characters

### Command

```bash
echo "The price of an Apple today is: \$HK $PRICE_PER_APPLE"
```

### Output

```text
The price of an Apple today is: $HK 5
```

### Explanation

The backslash `\` escapes the `$` sign so that it is printed literally.

---

# Example 4 – Using Curly Braces

### Command

```bash
echo "The first 10 letters in the alphabet are: ${MyFirstLetters}DEFGHIJ"
```

### Output

```text
The first 10 letters in the alphabet are: ABCDEFGHIJ
```

### Explanation

`${}` clearly defines where the variable name ends.

Without curly braces, the shell could interpret characters immediately following the variable name as part of the variable name.

---

# Example 5 – Quoted vs Unquoted Variables

Consider:

```bash
greeting='Hello        world!'
```

The value contains multiple spaces between `Hello` and `world!`.

### Without Quotes

```bash
echo $greeting
```

### Output

```text
Hello world!
```

The shell performs word splitting, so the multiple spaces are not preserved.

### With Double Quotes

```bash
echo "$greeting"
```

### Output

```text
Hello        world!
```

The double quotes preserve the complete value, including the multiple spaces.

### Difference

| Command | Output | Reason |
|---|---|---|
| `echo $greeting` | `Hello world!` | Word splitting occurs |
| `echo "$greeting"` | `Hello        world!` | Whitespace is preserved |

### General Rule

Prefer:

```bash
echo "$greeting"
```

instead of:

```bash
echo $greeting
```

Quoting variable expansions helps prevent unexpected word splitting.

---

# Practical Example – Using Variables

Suppose a script needs to display information about a user and the course they are learning.

```bash
#!/bin/bash

USERNAME="Poorvik"
COURSE="Linux"

echo "Hello, $USERNAME!"
echo "You are currently learning $COURSE."
```

### Output

```text
Hello, Poorvik!
You are currently learning Linux.
```

### Why This Is Useful

Instead of hard-coding the same values throughout a script, variables allow the values to be changed in one place.

---

# Practical Applications

- Shell scripting
- Storing configuration values
- Reusing values in scripts
- Automating Linux tasks
- Handling text and strings
- Creating reusable scripts

---

# Key Learnings

- Variables are created using `=`.
- Variables are referenced using `$`.
- `${}` can clearly define a variable name.
- `\` can escape special characters.
- Double quotes preserve whitespace in variable expansions.
- `echo "$variable"` is generally safer than `echo $variable`.
