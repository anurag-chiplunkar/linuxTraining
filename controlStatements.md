## Shell Conditional Statements: A Detailed Tutorial

Conditional statements are fundamental in shell scripting, allowing scripts to make decisions and execute different commands based on certain conditions. This tutorial covers the various types of conditional statements in shell scripting, including `if`, `else`, `elif`, and `case`.

### 1. The `if` Statement

The `if` statement is used to evaluate a condition and execute a block of code if the condition is true.

#### Syntax
```sh
if [ condition ]; then
    # Commands to execute if condition is true
fi
```

#### Example
```sh
#!/bin/bash

number=10

if [ $number -gt 5 ]; then
    echo "The number is greater than 5."
fi
```

### 2. The `if-else` Statement

The `if-else` statement adds an alternative block of code to execute if the condition is false.

#### Syntax
```sh
if [ condition ]; then
    # Commands to execute if condition is true
else
    # Commands to execute if condition is false
fi
```

#### Example
```sh
#!/bin/bash

number=3

if [ $number -gt 5 ]; then
    echo "The number is greater than 5."
else
    echo "The number is 5 or less."
fi
```

### 3. The `if-elif-else` Statement

The `if-elif-else` statement allows for multiple conditions to be checked in sequence.

#### Syntax
```sh
if [ condition1 ]; then
    # Commands to execute if condition1 is true
elif [ condition2 ]; then
    # Commands to execute if condition2 is true
else
    # Commands to execute if none of the above conditions are true
fi
```

#### Example
```sh
#!/bin/bash

number=7

if [ $number -gt 10 ]; then
    echo "The number is greater than 10."
elif [ $number -gt 5 ]; then
    echo "The number is greater than 5 but less than or equal to 10."
else
    echo "The number is 5 or less."
fi
```

### 4. The `case` Statement

The `case` statement is used to match a variable against a series of patterns and execute corresponding commands.

#### Syntax
```sh
case $variable in
    pattern1)
        # Commands to execute if pattern1 matches
        ;;
    pattern2)
        # Commands to execute if pattern2 matches
        ;;
    *)
        # Commands to execute if no patterns match
        ;;
esac
```

#### Example
```sh
#!/bin/bash

fruit="apple"

case $fruit in
    apple)
        echo "You have an apple."
        ;;
    banana)
        echo "You have a banana."
        ;;
    *)
        echo "Unknown fruit."
        ;;
esac
```

### Practical Examples

#### Example 1: Checking File Existence

```sh
#!/bin/bash

file="example.txt"

if [ -e $file ]; then
    echo "The file exists."
else
    echo "The file does not exist."
fi
```

#### Example 2: Multiple Conditions with `if-elif-else`

```sh
#!/bin/bash

read -p "Enter your score: " score

if [ $score -ge 90 ]; then
    echo "Grade: A"
elif [ $score -ge 80 ]; then
    echo "Grade: B"
elif [ $score -ge 70 ]; then
    echo "Grade: C"
elif [ $score -ge 60 ]; then
    echo "Grade: D"
else
    echo "Grade: F"
fi
```

#### Example 3: Using `case` for Menu Selection

```sh
#!/bin/bash

echo "Select an option:"
echo "1. Display date and time"
echo "2. List files"
echo "3. Display current directory"
echo "4. Exit"
read -p "Enter your choice [1-4]: " choice

case $choice in
    1)
        date
        ;;
    2)
        ls
        ;;
    3)
        pwd
        ;;
    4)
        echo "Exiting..."
        ;;
    *)
        echo "Invalid option."
        ;;
esac
```

### Explanation of Conditions

#### Conditions with Test Command (`[ ]`)

- Numeric comparisons:
  - `-eq`: equal to
  - `-ne`: not equal to
  - `-lt`: less than
  - `-le`: less than or equal to
  - `-gt`: greater than
  - `-ge`: greater than or equal to

- String comparisons:
  - `=`: equal to
  - `!=`: not equal to
  - `<`: less than (lexicographical)
  - `>`: greater than (lexicographical)
  - `-z`: string is null (zero length)
  - `-n`: string is not null (non-zero length)

- File conditions:
  - `-e`: file exists
  - `-f`: file is a regular file
  - `-d`: directory exists
  - `-r`: file is readable
  - `-w`: file is writable
  - `-x`: file is executable

#### Example: Using Various Conditions

```sh
#!/bin/bash

num1=10
num2=20
str1="hello"
str2="world"
file="test.txt"

# Numeric comparison
if [ $num1 -eq $num2 ]; then
    echo "Numbers are equal."
else
    echo "Numbers are not equal."
fi

# String comparison
if [ "$str1" = "$str2" ]; then
    echo "Strings are equal."
else
    echo "Strings are not equal."
fi

# File condition
if [ -e $file ]; then
    echo "File exists."
else
    echo "File does not exist."
fi
```

### Conclusion

Understanding and using conditional statements effectively is crucial for writing robust shell scripts. The `if`, `else`, `elif`, and `case` statements allow for flexible and powerful decision-making capabilities. By practicing these examples and experimenting with different conditions, you can become proficient in using conditional statements in your shell scripts.


## Shell Looping Statements: A Detailed Tutorial

Looping statements in shell scripting allow you to execute a set of commands repeatedly until a certain condition is met. This tutorial covers the various types of looping statements in shell scripting, including `for`, `while`, and `until` loops.

### 1. The `for` Loop

The `for` loop iterates over a list of items and executes a block of commands for each item in the list.

#### Syntax
```sh
for variable in list
do
    # Commands to execute for each item
done
```

#### Example
```sh
#!/bin/bash

for item in apple banana cherry
do
    echo "Fruit: $item"
done
```

### 2. The `while` Loop

The `while` loop executes a block of commands as long as a specified condition is true.

#### Syntax
```sh
while [ condition ]
do
    # Commands to execute while condition is true
done
```

#### Example
```sh
#!/bin/bash

counter=1

while [ $counter -le 5 ]
do
    echo "Counter: $counter"
    ((counter++))
done
```

### 3. The `until` Loop

The `until` loop is similar to the `while` loop, but it executes a block of commands as long as a specified condition is false.

#### Syntax
```sh
until [ condition ]
do
    # Commands to execute until condition becomes true
done
```

#### Example
```sh
#!/bin/bash

counter=1

until [ $counter -gt 5 ]
do
    echo "Counter: $counter"
    ((counter++))
done
```

### 4. Nested Loops

You can nest loops within each other, meaning you can place one loop inside another.

#### Example
```sh
#!/bin/bash

for i in 1 2 3
do
    for j in a b c
    do
        echo "i: $i, j: $j"
    done
done
```

### Practical Examples

#### Example 1: Iterating Over a List of Files

```sh
#!/bin/bash

for file in *.txt
do
    echo "Processing file: $file"
    # You can add commands to process each file here
done
```

#### Example 2: Reading User Input with a `while` Loop

```sh
#!/bin/bash

read -p "Enter a number (0 to exit): " num

while [ $num -ne 0 ]
do
    echo "You entered: $num"
    read -p "Enter another number (0 to exit): " num
done

echo "Exiting..."
```

#### Example 3: Counting Down with an `until` Loop

```sh
#!/bin/bash

counter=10

until [ $counter -lt 1 ]
do
    echo "Counter: $counter"
    ((counter--))
done
```

#### Example 4: Using a `for` Loop with a Range of Numbers

```sh
#!/bin/bash

for number in {1..5}
do
    echo "Number: $number"
done
```

### Explanation of Loop Control Statements

#### `break` Statement

The `break` statement is used to exit from a loop before it has finished executing.

#### Example
```sh
#!/bin/bash

for i in {1..10}
do
    if [ $i -eq 5 ]; then
        break
    fi
    echo "i: $i"
done
```

#### `continue` Statement

The `continue` statement is used to skip the current iteration of a loop and proceed to the next iteration.

#### Example
```sh
#!/bin/bash

for i in {1..5}
do
    if [ $i -eq 3 ]; then
        continue
    fi
    echo "i: $i"
done
```

### Real-World Example: Processing Log Files

#### Scenario

You have a directory of log files, and you want to extract and count the number of error messages in each file.

#### Script
```sh
#!/bin/bash

for logfile in /path/to/logs/*.log
do
    echo "Processing $logfile"
    error_count=$(grep -c "ERROR" "$logfile")
    echo "Number of errors: $error_count"
done
```

### Conclusion

Looping statements are powerful tools in shell scripting that allow you to automate repetitive tasks. By understanding and using `for`, `while`, and `until` loops effectively, you can create more efficient and flexible scripts. The provided examples and explanations should help you get started with using loops in your own shell scripts.