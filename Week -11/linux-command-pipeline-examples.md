# Linux Command Pipeline Examples

## 📌 Overview

Linux pipelines allow multiple commands to work together by passing the output of one command as the input to another.

```bash
command1 | command2 | command3
```

Pipelines are widely used in Linux administration, shell scripting, and cybersecurity for processing logs and analyzing large amounts of data.

---

# Example 1 – Count Total Lines

### Command

```bash
cat access.log | wc -l
```

### Explanation

- `cat` displays the file.
- `wc -l` counts the number of lines.

---

# Example 2 – Count Total Words

### Command

```bash
cat notes.txt | wc -w
```

### Explanation

Counts the total number of words in the file.

---

# Example 3 – Count Characters

### Command

```bash
cat file.txt | wc -m
```

### Explanation

Counts the total number of characters.

---

# Example 4 – Display First Five Lines

```bash
head -5 file.txt
```

---

# Example 5 – Display Last Five Lines

```bash
tail -5 file.txt
```

---

# Example 6 – Extract Usernames from /etc/passwd

```bash
cut -d ":" -f1 /etc/passwd
```

---

# Example 7 – Display Unique Entries

```bash
sort file.txt | uniq
```

---

# Example 8 – Count Frequency of Words

```bash
sort file.txt | uniq -c
```

---

# Example 9 – Most Frequent Word

```bash
sort file.txt | uniq -c | sort -nr | head -1
```

### Explanation

- Sort the file
- Count duplicate occurrences
- Sort numerically in descending order
- Display the highest occurrence

---

# Example 10 – Most Frequent IP Address

```bash
awk '{print $1}' access.log | sort | uniq -c | sort -nr | head -5
```

### Explanation

- Extract IP addresses
- Sort
- Count occurrences
- Display the top five

---

# Example 11 – Count Failed Login Attempts

```bash
grep "Failed" auth.log | wc -l
```

---

# Example 12 – Find ERROR Messages

```bash
grep "ERROR" server.log
```

---

# Example 13 – Display Only Required Column

```bash
cut -d "," -f2 employees.csv
```

---

# Example 14 – Sort Employees by Salary

```bash
sort -t "," -k3 -nr employees.csv
```

---

# Example 15 – Display Engineering Employees

```bash
grep "Engineering" employees.csv
```

---

# Example 16 – Display Engineering Employee Names

```bash
grep "Engineering" employees.csv | cut -d "," -f2
```

---

# Example 17 – Join Two Files

```bash
join -1 3 -2 1 employees.txt departments.txt
```

---

# Example 18 – Custom Join Output

```bash
join -o 1.2,1.3,2.2 employees.txt departments.txt
```

---

# Example 19 – Create Files Using xargs

```bash
cat books.txt | xargs -I {} touch {}.txt
```

---

# Example 20 – Execute Commands in Parallel

```bash
cat books.txt | xargs -P 3 -I {} ./process-book.sh {}
```

---

# Example 21 – Process Batches

```bash
cat books.txt | xargs -n 2 echo
```

---

# Example 22 – Print First Field Using AWK

```bash
awk '{print $1}' students.txt
```

---

# Example 23 – Print Multiple Fields

```bash
awk '{print $1,$3}' students.txt
```

---

# Example 24 – Filter Records

```bash
awk '$2 > 80' students.txt
```

---

# Example 25 – Count Total Records

```bash
awk 'END {print NR}' students.txt
```

---

# Example 26 – Count Total Words

```bash
awk '{count += NF} END {print count}' file.txt
```

---

# Example 27 – Display Username and Shell

```bash
awk -F ":" '{print $1,$7}' /etc/passwd
```

---

# Common Pipeline Pattern

```
Input File
     │
     ▼
grep
     │
     ▼
cut / awk
     │
     ▼
sort
     │
     ▼
uniq
     │
     ▼
sort -nr
     │
     ▼
head
```

---

# Practical Applications

- Log analysis
- User account analysis
- Report generation
- Text processing
- Data filtering
- Counting occurrences
- Identifying top records
- Processing CSV files
- Linux system administration
- Cybersecurity investigations

---

# Key Learnings

- Linux commands become much more powerful when combined using pipelines.
- `grep` filters data.
- `cut` and `awk` extract required fields.
- `sort` organizes data.
- `uniq` removes duplicates or counts occurrences.
- `head` and `tail` display specific portions of output.
- `xargs` automates repetitive command execution.
- Combining simple commands solves complex real-world problems efficiently.
