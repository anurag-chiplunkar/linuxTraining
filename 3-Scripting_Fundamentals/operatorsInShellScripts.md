### Scripting Fundamentals: Operators in Shell Scripts

#### Theory

**Operators in Shell Scripts**:
Operators are symbols that tell the shell to perform specific operations on variables and values. Shell scripting supports various types of operators, including arithmetic, relational, and logical operators.

**1. Arithmetic Operators**:
- Used to perform basic arithmetic operations.
- Operators: `+`, `-`, `*`, `/`, `%` (modulus)
- Example:
  ```bash
  #!/bin/bash
  a=10
  b=5
  sum=$((a + b))
  echo "Sum: $sum"
  ```

**2. Relational Operators**:
- Used to compare two values.
- Operators: `-eq` (equal to), `-ne` (not equal to), `-gt` (greater than), `-lt` (less than), `-ge` (greater than or equal to), `-le` (less than or equal to)
- Example:
  ```bash
  #!/bin/bash
  a=10
  b=5
  if [ $a -gt $b ]; then
    echo "$a is greater than $b"
  fi
  ```

**3. Logical Operators**:
- Used to perform logical operations.
- Operators: `&&` (logical AND), `||` (logical OR), `!` (logical NOT)
- Example:
  ```bash
  #!/bin/bash
  a=10
  b=5
  if [ $a -gt $b ] && [ $a -gt 0 ]; then
    echo "$a is greater than $b and positive"
  fi
  ```

#### Example Scripts

1. **Arithmetic Operations**:
   ```bash
   #!/bin/bash

   # Declare variables
   num1=10
   num2=5

   # Perform arithmetic operations
   sum=$((num1 + num2))
   diff=$((num1 - num2))
   prod=$((num1 * num2))
   quot=$((num1 / num2))
   mod=$((num1 % num2))

   # Display results
   echo "Sum: $sum"
   echo "Difference: $diff"
   echo "Product: $prod"
   echo "Quotient: $quot"
   echo "Modulus: $mod"
   ```

2. **Relational Operations**:
   ```bash
   #!/bin/bash

   # Declare variables
   a=10
   b=20

   # Perform relational operations
   if [ $a -eq $b ]; then
     echo "$a is equal to $b"
   elif [ $a -ne $b ]; then
     echo "$a is not equal to $b"
   fi

   if [ $a -gt $b ]; then
     echo "$a is greater than $b"
   elif [ $a -lt $b ]; then
     echo "$a is less than $b"
   fi

   if [ $a -ge $b ]; then
     echo "$a is greater than or equal to $b"
   elif [ $a -le $b ]; then
     echo "$a is less than or equal to $b"
   fi
   ```

3. **Logical Operations**:
   ```bash
   #!/bin/bash

   # Declare variables
   a=10
   b=20

   # Perform logical operations
   if [ $a -lt $b ] && [ $a -gt 0 ]; then
     echo "$a is less than $b and positive"
   fi

   if [ $a -gt $b ] || [ $a -lt 0 ]; then
     echo "$a is either greater than $b or negative"
   fi

   if [ ! $a -eq $b ]; then
     echo "$a is not equal to $b"
   fi
   ```

4. **Combination of Arithmetic and Relational Operations**:
   ```bash
   #!/bin/bash

   # Declare variables
   num1=15
   num2=25
   sum=$((num1 + num2))

   # Perform relational operation
   if [ $sum -gt 30 ]; then
     echo "The sum of $num1 and $num2 is greater than 30"
   else
     echo "The sum of $num1 and $num2 is less than or equal to 30"
   fi
   ```

5. **Check File Permissions Using Logical Operators**:
   ```bash
   #!/bin/bash

   # File to check
   file="example.txt"

   # Check file permissions
   if [ -e $file ] && [ -r $file ]; then
     echo "$file exists and is readable"
   else
     echo "$file does not exist or is not readable"
   fi
   ```

#### Practice Problem Statements

1. **Even or Odd**:
   - Write a script named `evenodd.sh` to check if a number is even or odd.
   ```bash
   #!/bin/bash

   # Prompt user for a number
   echo "Enter a number:"
   read num

   # Check if the number is even or odd
   if [ $((num % 2)) -eq 0 ]; then
     echo "$num is even"
   else
     echo "$num is odd"
   fi
   ```

2. **Greatest of Three Numbers**:
   - Write a script named `greatest.sh` to find the greatest of three numbers.
   ```bash
   #!/bin/bash

   # Prompt user for three numbers
   echo "Enter three numbers:"
   read a b c

   # Find the greatest number
   if [ $a -ge $b ] && [ $a -ge $c ]; then
     echo "$a is the greatest"
   elif [ $b -ge $a ] && [ $b -ge $c ]; then
     echo "$b is the greatest"
   else
     echo "$c is the greatest"
   fi
   ```

3. **Leap Year Check**:
   - Write a script named `leapyear.sh` to check if a year is a leap year.
   ```bash
   #!/bin/bash

   # Prompt user for a year
   echo "Enter a year:"
   read year

   # Check if the year is a leap year
   if [ $((year % 4)) -eq 0 ] && { [ $((year % 100)) -ne 0 ] || [ $((year % 400)) -eq 0 ]; }; then
     echo "$year is a leap year"
   else
     echo "$year is not a leap year"
   fi
   ```

4. **Simple Calculator**:
   - Write a script named `simplecalc.sh` to perform basic arithmetic operations based on user input.
   ```bash
   #!/bin/bash

   # Prompt user for two numbers
   echo "Enter first number:"
   read num1
   echo "Enter second number:"
   read num2

   # Perform arithmetic operations
   sum=$((num1 + num2))
   diff=$((num1 - num2))
   prod=$((num1 * num2))
   quot=$((num1 / num2))
   mod=$((num1 % num2))

   # Display results
   echo "Sum: $sum"
   echo "Difference: $diff"
   echo "Product: $prod"
   echo "Quotient: $quot"
   echo "Modulus: $mod"
   ```

5. **File Comparison**:
   - Write a script named `filecompare.sh` to compare the size of two files.
   ```bash
   #!/bin/bash

   # Prompt user for two filenames
   echo "Enter first filename:"
   read file1
   echo "Enter second filename:"
   read file2

   # Compare file sizes
   size1=$(stat -c%s "$file1")
   size2=$(stat -c%s "$file2")

   if [ $size1 -gt $size2 ]; then
     echo "$file1 is larger than $file2"
   elif [ $size1 -lt $size2 ]; then
     echo "$file1 is smaller than $file2"
   else
     echo "$file1 and $file2 are of the same size"
   fi
   ```
