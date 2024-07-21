### Scripting Fundamentals: Looping Statements (for, while, until)

#### Theory

**Looping Statements**:
Looping statements in shell scripts are used to execute a block of code repeatedly based on a condition. The `for`, `while`, and `until` loops are commonly used to perform iterative operations.

**1. `for` Loop**:
- Used to iterate over a list of values or a range.
- Syntax:
  ```bash
  for variable in list; do
    # Code to execute for each item in the list
  done
  ```

**2. `while` Loop**:
- Executes a block of code as long as a specified condition is true.
- Syntax:
  ```bash
  while [ condition ]; do
    # Code to execute while the condition is true
  done
  ```

**3. `until` Loop**:
- Executes a block of code as long as a specified condition is false.
- Syntax:
  ```bash
  until [ condition ]; do
    # Code to execute until the condition becomes true
  done
  ```

#### Example Scripts

1. **for Loop to Print Numbers 1 to 5**:
   ```bash
   #!/bin/bash

   for i in {1..5}; do
     echo "Number: $i"
   done
   ```

2. **while Loop to Print Numbers 1 to 5**:
   ```bash
   #!/bin/bash

   i=1
   while [ $i -le 5 ]; do
     echo "Number: $i"
     ((i++))
   done
   ```

3. **until Loop to Print Numbers 1 to 5**:
   ```bash
   #!/bin/bash

   i=1
   until [ $i -gt 5 ]; do
     echo "Number: $i"
     ((i++))
   done
   ```

4. **for Loop to Iterate Over a List of Strings**:
   ```bash
   #!/bin/bash

   for fruit in apple banana cherry; do
     echo "Fruit: $fruit"
   done
   ```

5. **while Loop to Read Lines from a File**:
   ```bash
   #!/bin/bash

   file="example.txt"
   while IFS= read -r line; do
     echo "Line: $line"
   done < "$file"
   ```

#### Practice Problem Statements

1. **Print Even Numbers from 1 to 10 Using a for Loop**:
   - Write a script named `even_numbers.sh` to print even numbers from 1 to 10.
   ```bash
   #!/bin/bash

   for i in {1..10}; do
     if [ $((i % 2)) -eq 0 ]; then
       echo "Even number: $i"
     fi
   done
   ```

2. **Calculate the Sum of Numbers from 1 to 100 Using a while Loop**:
   - Write a script named `sum_numbers.sh` to calculate the sum of numbers from 1 to 100.
   ```bash
   #!/bin/bash

   sum=0
   i=1
   while [ $i -le 100 ]; do
     sum=$((sum + i))
     ((i++))
   done
   echo "Sum: $sum"
   ```

3. **Print Multiplication Table of 5 Using an until Loop**:
   - Write a script named `multiplication_table.sh` to print the multiplication table of 5.
   ```bash
   #!/bin/bash

   i=1
   until [ $i -gt 10 ]; do
     echo "5 * $i = $((5 * i))"
     ((i++))
   done
   ```

4. **Print the Names of All Files in the Current Directory Using a for Loop**:
   - Write a script named `list_files.sh` to print the names of all files in the current directory.
   ```bash
   #!/bin/bash

   for file in *; do
     if [ -f "$file" ]; then
       echo "File: $file"
     fi
   done
   ```

5. **Read and Print Each Line from a File Using a while Loop**:
   - Write a script named `read_file.sh` to read and print each line from a file.
   ```bash
   #!/bin/bash

   file="example.txt"
   while IFS= read -r line; do
     echo "Line: $line"
   done < "$file"
   ```

#### Teaching Examples

1. **for Loop to Print Numbers 1 to 10**:
   ```bash
   #!/bin/bash

   for i in {1..10}; do
     echo "Number: $i"
   done
   ```

2. **while Loop to Calculate Factorial of a Number**:
   ```bash
   #!/bin/bash

   echo "Enter a number:"
   read num
   factorial=1
   i=1
   while [ $i -le $num ]; do
     factorial=$((factorial * i))
     ((i++))
   done
   echo "Factorial of $num is $factorial"
   ```

3. **until Loop to Print a Countdown from 10 to 1**:
   ```bash
   #!/bin/bash

   i=10
   until [ $i -lt 1 ]; do
     echo "Countdown: $i"
     ((i--))
   done
   ```

4. **for Loop to Iterate Over a List of Numbers**:
   ```bash
   #!/bin/bash

   for num in 1 2 3 4 5; do
     echo "Number: $num"
   done
   ```

5. **while Loop to Validate User Input**:
   ```bash
   #!/bin/bash

   while true; do
     echo "Enter a number between 1 and 10:"
     read num
     if [ $num -ge 1 ] && [ $num -le 10 ]; then
       echo "Valid input: $num"
       break
     else
       echo "Invalid input. Please try again."
     fi
   done
   ```

#### Practice Problems

1. **Print Odd Numbers from 1 to 20 Using a for Loop**:
   - Write a script named `odd_numbers.sh` to print odd numbers from 1 to 20.
   ```bash
   #!/bin/bash

   for i in {1..20}; do
     if [ $((i % 2)) -ne 0 ]; then
       echo "Odd number: $i"
     fi
   done
   ```

2. **Calculate the Product of Numbers from 1 to 10 Using a while Loop**:
   - Write a script named `product_numbers.sh` to calculate the product of numbers from 1 to 10.
   ```bash
   #!/bin/bash

   product=1
   i=1
   while [ $i -le 10 ]; do
     product=$((product * i))
     ((i++))
   done
   echo "Product: $product"
   ```

3. **Print the First 10 Fibonacci Numbers Using an until Loop**:
   - Write a script named `fibonacci.sh` to print the first 10 Fibonacci numbers.
   ```bash
   #!/bin/bash

   a=0
   b=1
   i=1
   until [ $i -gt 10 ]; do
     echo "Fibonacci number $i: $a"
     next=$((a + b))
     a=$b
     b=$next
     ((i++))
   done
   ```

4. **Print the Names of All Directories in the Current Directory Using a for Loop**:
   - Write a script named `list_directories.sh` to print the names of all directories in the current directory.
   ```bash
   #!/bin/bash

   for dir in *; do
     if [ -d "$dir" ]; then
       echo "Directory: $dir"
     fi
   done
   ```

5. **Count the Number of Lines in a File Using a while Loop**:
   - Write a script named `count_lines.sh` to count the number of lines in a file.
   ```bash
   #!/bin/bash

   file="example.txt"
   count=0
   while IFS= read -r line; do
     ((count++))
   done < "$file"
   echo "Number of lines: $count"
   ```
