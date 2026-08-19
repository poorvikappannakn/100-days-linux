# Shell Arrays

## 📌 Overview

Shell arrays allow multiple values to be stored in a single variable. An array can contain multiple elements, and individual elements can be accessed using their index.

---

# Example 1 – Creating an Array

### Command

```bash
#!/bin/bash

array=("Hello" "Hi")
```

### Explanation

* `array` is the name of the array.
* `=("Hello" "Hi")` assigns multiple elements to the array.
* Array elements are separated by spaces.
* The first element is stored at index `0`.
* The second element is stored at index `1`.

---

# Example 2 – Finding the Number of Elements

### Command

```bash
echo "${#array[@]}"
```

### Output

```text
2
```

### Explanation

* `${#array[@]}` gives the number of elements in the array.
* In this example, the array contains two elements: `Hello` and `Hi`.

---

# Example 3 – Accessing an Array Element

### Command

```bash
echo "${array[1]}"
```

### Output

```text
Hi
```

### Explanation

Array indexing starts from `0`.

For the array:

```bash
array=("Hello" "Hi")
```

* `array[0]` → `Hello`
* `array[1]` → `Hi`

Therefore, `${array[1]}` accesses the second element.

---

# Example 4 – Accessing Multiple Array Elements

### Command

```bash
echo "${array[0]}"
echo "${array[1]}"
```

### Output

```text
Hello
Hi
```

### Explanation

Each array element can be accessed individually using its index.

---

# 🚀 Key Learnings

* Shell arrays can store multiple values in a single variable.
* Array elements are separated by spaces when the array is created.
* Array indexing starts from `0`.
* `${array[0]}` accesses the first element.
* `${array[1]}` accesses the second element.
* `${#array[@]}` gives the total number of elements in the array.
