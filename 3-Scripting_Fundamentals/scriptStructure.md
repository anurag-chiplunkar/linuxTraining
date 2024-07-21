### Scripting Fundamentals: Script Structure

#### Theory

**Script Structure**:
A well-structured shell script enhances readability, maintainability, and debugging. A typical script includes the shebang line, comments, and the script body.

**Shebang Line (`#!/bin/bash`)**:
Indicates the script interpreter, ensuring the script runs with the specified shell.

**Comments**:
- Start with `#` and are not executed.
- Used to explain the code, providing context and clarity.
- Essential for maintaining and understanding the script.

**Script Body**:
- Contains the commands and logic that perform the script's intended tasks.
- May include variable declarations, loops, conditionals, functions, and command executions.

**Basic Structure**:
```bash
#!/bin/bash

# Script to demonstrate basic structure

# Declare variables
name="Alice"
age=30

# Print variables
echo "Name: $name"
echo "Age: $age"

# End of script
```

#### Example Scripts

1. **Simple Commented Script**:
   ```bash
   #!/bin/bash

   # This script prints a welcome message

   echo "Welcome to shell scripting!"
   ```

2. **Script with Variables and Comments**:
   ```bash
   #!/bin/bash

   # This script prints the user's name and age

   # Declare variables
   name="John"
   age=25

   # Print variables
   echo "Name: $name"
   echo "Age: $age"
   ```

3. **Script with Conditional Statements**:
   ```bash
   #!/bin/bash

   # This script checks if a number is positive or negative

   # Declare variable
   number=-5

   # Check if number is positive or negative
   if [ $number -gt 0 ]; then
     echo "The number is positive."
   else
     echo "The number is negative."
   fi
   ```

4. **Script with Loops**:
   ```bash
   #!/bin/bash

   # This script prints numbers from 1 to 5

   # Loop from 1 to 5
   for i in {1..5}; do
     echo "Number: $i"
   done
   ```

5. **Script with Functions**:
   ```bash
   #!/bin/bash

   # This script demonstrates the use of functions

   # Function to print a greeting
   greet() {
     echo "Hello, $1!"
   }

   # Call the function with a name
   greet "Alice"
   ```

#### Practice Problem Statements

1. **Print System Information**:
   - Write a script named `sysinfo.sh` to display system information.
   ```bash
   #!/bin/bash

   # This script displays system information

   # Print hostname
   echo "Hostname: $(hostname)"

   # Print current date and time
   echo "Date and Time: $(date)"

   # Print current user
   echo "Current User: $USER"
   ```

2. **Check File Existence**:
   - Write a script named `checkfile.sh` to check if a file exists.
   ```bash
   #!/bin/bash

   # This script checks if a file exists

   # File to check
   file="test.txt"

   # Check if file exists
   if [ -e $file ]; then
     echo "File $file exists."
   else
     echo "File $file does not exist."
   fi
   ```

3. **Calculate Factorial**:
   - Write a script named `factorial.sh` to calculate the factorial of a number.
   ```bash
   #!/bin/bash

   # This script calculates the factorial of a number

   # Number to calculate factorial
   number=5

   # Initialize factorial
   factorial=1

   # Calculate factorial using a loop
   for ((i=1; i<=number; i++)); do
     factorial=$((factorial * i))
   done

   # Print factorial
   echo "Factorial of $number is $factorial"
   ```

4. **Backup Files**:
   - Write a script named `backup.sh` to back up files from one directory to another.
   ```bash
   #!/bin/bash

   # This script backs up files from source to destination directory

   # Source and destination directories
   src="/path/to/source"
   dest="/path/to/destination"

   # Copy files from source to destination
   cp -r $src/* $dest

   # Print message
   echo "Backup completed."
   ```

5. **Simple Calculator**:
   - Write a script named `calculator.sh` to perform basic arithmetic operations.
   ```bash
   #!/bin/bash

   # This script performs basic arithmetic operations

   # Numbers to calculate
   a=10
   b=5

   # Perform arithmetic operations
   sum=$((a + b))
   diff=$((a - b))
   prod=$((a * b))
   quot=$((a / b))

   # Print results
   echo "Sum: $sum"
   echo "Difference: $diff"
   echo "Product: $prod"
   echo "Quotient: $quot"
   ```
