# Arithmetic Operations

## 📌 Overview

Bash provides the `$((expression))` syntax for performing arithmetic operations.

Arithmetic operations can be performed using shell variables.

---

# Example 1 – Create Numeric Variables

### Script

```bash
#!/bin/bash

X=10
Y=5
```

These variables can then be used in arithmetic expressions.

---

# Example 2 – Addition

### Command

```bash
SUM=$((X + Y))
echo "Sum of $X and $Y is: $SUM"
```

### Output

```text
Sum of 10 and 5 is: 15
```

---

# Example 3 – Subtraction

### Command

```bash
DIFF=$((X - Y))
echo "Difference between $X and $Y is: $DIFF"
```

### Output

```text
Difference between 10 and 5 is: 5
```

---

# Example 4 – Multiplication

### Command

```bash
PRODUCT=$((X * Y))
echo "Product of $X and $Y is: $PRODUCT"
```

### Output

```text
Product of 10 and 5 is: 50
```

---

# Example 5 – Division

### Command

```bash
QUOTIENT=$((X / Y))
echo "Quotient of $X divided by $Y is: $QUOTIENT"
```

### Output

```text
Quotient of 10 divided by 5 is: 2
```

---

# Example 6 – Modulus

### Command

```bash
REMAINDER=$((X % Y))
echo "Remainder of $X divided by $Y is: $REMAINDER"
```

### Output

```text
Remainder of 10 divided by 5 is: 0
```

The modulus operator `%` returns the remainder after division.

---

# Example 7 – Increment

### Command

```bash
X=$((X + 1))
echo "After incrementing, X is now: $X"
```

### Output

```text
After incrementing, X is now: 11
```

---

# Example 8 – Decrement

### Command

```bash
Y=$((Y - 1))
echo "After decrementing, Y is now: $Y"
```

### Output

```text
After decrementing, Y is now: 4
```

---

# Arithmetic Operators

| Operator | Operation |
|---|---|
| `+` | Addition |
| `-` | Subtraction |
| `*` | Multiplication |
| `/` | Division |
| `%` | Modulus |

---

# Complete Example

```bash
#!/bin/bash

X=10
Y=5

SUM=$((X + Y))
echo "Sum of $X and $Y is: $SUM"

DIFF=$((X - Y))
echo "Difference between $X and $Y is: $DIFF"

PRODUCT=$((X * Y))
echo "Product of $X and $Y is: $PRODUCT"

QUOTIENT=$((X / Y))
echo "Quotient of $X divided by $Y is: $QUOTIENT"

REMAINDER=$((X % Y))
echo "Remainder of $X divided by $Y is: $REMAINDER"

X=$((X + 1))
echo "After incrementing, X is now: $X"

Y=$((Y - 1))
echo "After decrementing, Y is now: $Y"
```

### Output

```text
Sum of 10 and 5 is: 15
Difference between 10 and 5 is: 5
Product of 10 and 5 is: 50
Quotient of 10 divided by 5 is: 2
Remainder of 10 divided by 5 is: 0
After incrementing, X is now: 11
After decrementing, Y is now: 4
```

---

# Practical Example – Calculate Total Cost

Suppose a script needs to calculate the total cost of buying several items.

```bash
#!/bin/bash

PRICE_PER_APPLE=5
NUMBER_OF_APPLES=6

TOTAL=$((PRICE_PER_APPLE * NUMBER_OF_APPLES))

echo "Price per apple: $PRICE_PER_APPLE"
echo "Number of apples: $NUMBER_OF_APPLES"
echo "Total cost: $TOTAL"
```

### Output

```text
Price per apple: 5
Number of apples: 6
Total cost: 30
```

### Why This Is Useful

Arithmetic operations allow Bash scripts to perform calculations automatically.

They can be used for:

- Counters
- Totals
- Simple calculations
- Automation
- Resource calculations

---

# Key Learnings

- Bash uses `$((expression))` for arithmetic.
- Variables can be used inside arithmetic expressions.
- Bash supports addition, subtraction, multiplication, division, and modulus.
- Variables can be incremented and decremented using arithmetic expressions.
