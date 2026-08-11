# Bash Shell Scripting — Loops & Case Statements

A collection of basic **Bash shell scripting** examples covering:

* `for` loops
* `while` loops
* `until` loops
* `case` statements
* User input with `read`
* Arithmetic operations

---

## 📁 Programs Covered

| # | Topic              | Description                                         |
| - | ------------------ | --------------------------------------------------- |
| 1 | For Loop           | Demonstrates two ways to use `for` loops            |
| 2 | While & Until Loop | Demonstrates `while` and `until` loops              |
| 3 | Case Statement     | Performs arithmetic operations based on user choice |

---

# 1. For Loop

This example demonstrates two different ways to create a `for` loop in Bash.

### Code

```bash
#!/bin/bash

echo "Learning Loops"

# C-style for loop
for ((i=0; i<10; i++))
do
    echo "$i"
done

echo "Another way"

# Range-based for loop
for i in {1..10}
do
    echo "$i"
done
```

### Output

```text
Learning Loops
0
1
2
3
4
5
6
7
8
9
Another way
1
2
3
4
5
6
7
8
9
10
```

### Explanation

The first loop uses the C-style syntax:

```bash
for ((initialization; condition; increment))
```

The second loop uses Bash's brace expansion:

```bash
for i in {1..10}
```

---

# 2. While and Until Loops

This example demonstrates how `while` and `until` loops work in Bash.

### Code

```bash
#!/bin/bash

echo "First Version"

i=15

while ((i < 25))
do
    echo "$i"
    i=$((i + 1))
done

echo "Another Version"

i=5

until ((i > 10))
do
    echo "$i"
    i=$((i + 1))
done
```

### Output

```text
First Version
15
16
17
18
19
20
21
22
23
24
Another Version
5
6
7
8
9
10
```

### Explanation

### `while` Loop

A `while` loop continues executing **as long as the condition is true**.

```bash
while ((i < 25))
do
    ...
done
```

Here, the loop runs while `i` is less than `25`.

### `until` Loop

An `until` loop continues executing **until the condition becomes true**.

```bash
until ((i > 10))
do
    ...
done
```

Starting with `i=5`, the loop runs until `i > 10`.

---

# 3. Case Statement with Arithmetic

This program accepts:

1. A user's choice
2. First number
3. Second number

It then performs an arithmetic operation based on the selected option.

### Code

```bash
#!/bin/bash

echo "Learning Loops"

read -p "Enter Choice: " ch
read -p "First Number: " f1
read -p "Second Number: " f2

case $ch in

    1)
        echo "Addition Of F1 & F2"
        echo "Add=$((f1 + f2))"
        ;;

    2)
        echo "Subtraction Of F1 & F2"
        echo "Sub=$((f1 - f2))"
        ;;

    *)
        echo "Default"
        echo "End Of Switch Case"
        ;;

esac
```

### Example

```text
Learning Loops
Enter Choice: 1
First Number: 10
Second Number: 20
Addition Of F1 & F2
Add=30
```

Another example:

```text
Learning Loops
Enter Choice: 2
First Number: 20
Second Number: 10
Subtraction Of F1 & F2
Sub=10
```

If the user enters any option other than `1` or `2`:

```text
Learning Loops
Enter Choice: 5
First Number: 10
Second Number: 20
Default
End Of Switch Case
```

---

# 4. File Access Using For Loop

This example demonstrates how to use a `for` loop to check whether files exist in the current directory.

## Code

```bash
#!/bin/bash

echo "Checking Files"

for file in file1.txt file2.txt file3.txt
do
    if [ -e "$file" ]
    then
        echo "$file exists"
    else
        echo "$file does not exist"
    fi
done
```

## Example Output

If `file1.txt` exists but `file2.txt` and `file3.txt` do not exist:

```text
Checking Files
file1.txt exists
file2.txt does not exist
file3.txt does not exist
```

## Explanation

The `for` loop checks each filename one by one:

```bash
for file in file1.txt file2.txt file3.txt
```

The `if` condition checks whether the file exists:

```bash
if [ -e "$file" ]
```

Here:

* `-e` → Checks whether a file or directory exists
* `$file` → Stores the current filename
* `echo` → Displays the result

---
## File Access Using For Loop

```bash
#!/bin/bash

for file in *
do
    echo "Checking: $file"

    if [ -e "$file" ]
    then
        echo "  File or directory exists"
    fi

    if [ -f "$file" ]
    then
        echo "  Regular file"
    fi

    if [ -d "$file" ]
    then
        echo "  Directory"
    fi

    if [ -r "$file" ]
    then
        echo "  File is readable"
    fi

    if [ -w "$file" ]
    then
        echo "  File is writable"
    fi

    if [ -x "$file" ]
    then
        echo "  File is executable"
    fi

    echo "--------------------"
done
```

### File Test Operators

| Operator | Meaning                  |
| -------- | ------------------------ |
| `-e`     | File or directory exists |
| `-f`     | Regular file exists      |
| `-d`     | Directory exists         |
| `-r`     | File is readable         |
| `-w`     | File is writable         |
| `-x`     | File is executable       |

### Example Output

```text
Checking: example.txt
  File or directory exists
  Regular file
  File is readable
  File is writable
--------------------
Checking: test
  File or directory exists
  Directory
  File is readable
  File is writable
--------------------
```

## Common File Tests

Bash provides several operators for checking files:

| Operator | Meaning                  |
| -------- | ------------------------ |
| `-e`     | File or directory exists |
| `-f`     | Regular file exists      |
| `-d`     | Directory exists         |
| `-r`     | File is readable         |
| `-w`     | File is writable         |
| `-x`     | File is executable       |

### Example

```bash
if [ -f "$file" ]
then
    echo "$file is a regular file"
fi
```

---

## Checking All `.txt` Files

Instead of manually providing filenames, we can use `*.txt` to check all text files in the current directory.

```bash
#!/bin/bash

echo "Checking Text Files"

for file in *.txt
do
    if [ -f "$file" ]
    then
        echo "$file is a text file"
    fi
done
```

### Example Output

```text
Checking Text Files
file1.txt is a text file
notes.txt is a text file
data.txt is a text file
```

This is useful when working with multiple files and performing file-related operations automatically.

# 🧠 Bash Concepts Used

## Shebang

```bash
#!/bin/bash
```

Specifies that the script should be executed using the Bash shell.

---

## Printing Output

```bash
echo "Hello World"
```

The `echo` command prints text to the terminal.

---

## Taking User Input

```bash
read -p "Enter Choice: " ch
```

The `read` command accepts input from the user and stores it in a variable.

---

## Arithmetic

Bash arithmetic can be performed using:

```bash
$((expression))
```

For example:

```bash
sum=$((10 + 20))
```

or:

```bash
echo "$((f1 + f2))"
```

---

## Incrementing a Variable

```bash
i=$((i + 1))
```

This increases the value of `i` by `1`.

---

# ▶️ How to Run

Make the script executable:

```bash
chmod +x script.sh
```

Then run it:

```bash
./script.sh
```

You can also run a Bash script directly with:

```bash
bash script.sh
```

---

# 📚 Topics Learned

* [x] Bash Shebang
* [x] `echo`
* [x] Variables
* [x] `read`
* [x] Arithmetic expressions
* [x] `for` loop
* [x] `while` loop
* [x] `until` loop
* [x] `case` statement
* [x] Conditional execution
* [x] User input

---

## 🚀 Next Steps

After understanding these basics, the next useful Bash topics to learn are:

1. `if`, `elif`, and `else`
2. Comparison operators
3. Logical operators
4. Functions
5. Arrays
6. Command-line arguments
7. File handling
8. String operations
9. Exit status and error handling
10. Practical Bash automation scripts


