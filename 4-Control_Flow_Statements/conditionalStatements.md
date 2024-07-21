### Scripting Fundamentals: Conditional Statements (if, else, elif)

#### Theory

**Conditional Statements**:
Conditional statements in shell scripts are used to make decisions based on certain conditions. The `if`, `else`, and `elif` statements are fundamental control flow structures that allow the execution of different blocks of code depending on whether a condition is true or false.

**1. `if` Statement**:
- Used to execute a block of code if a specified condition is true.
- Syntax:
  ```bash
  if [ condition ]; then
    # Code to execute if condition is true
  fi
  ```

**2. `else` Statement**:
- Used to execute a block of code if the `if` condition is false.
- Syntax:
  ```bash
  if [ condition ]; then
    # Code to execute if condition is true
  else
    # Code to execute if condition is false
  fi
  ```

**3. `elif` Statement**:
- Used to check multiple conditions.
- Syntax:
  ```bash
  if [ condition1 ]; then
    # Code to execute if condition1 is true
  elif [ condition2 ]; then
    # Code to execute if condition2 is true
  else
    # Code to execute if all conditions are false
  fi
  ```

**Example**:
```bash
#!/bin/bash

# Example of if, else, and elif statements

# Declare a variable
num=10

# if statement
if [ $num -gt 5 ]; then
  echo "$num is greater than 5"
fi

# if-else statement
if [ $num -lt 5 ]; then
  echo "$num is less than 5"
else
  echo "$num is not less than 5"
fi

# if-elif-else statement
if [ $num -lt 5 ]; then
  echo "$num is less than 5"
elif [ $num -eq 10 ]; then
  echo "$num is equal to 10"
else
  echo "$num is greater than 5 but not equal to 10"
fi
```

#### Example Scripts

1. **Check if a Number is Positive, Negative, or Zero**:
   ```bash
   #!/bin/bash

   # Prompt user for a number
   echo "Enter a number:"
   read num

   # Check if the number is positive, negative, or zero
   if [ $num -gt 0 ]; then
     echo "$num is positive"
   elif [ $num -lt 0 ]; then
     echo "$num is negative"
   else
     echo "$num is zero"
   fi
   ```

2. **Check if a File Exists**:
   ```bash
   #!/bin/bash

   # Prompt user for a filename
   echo "Enter a filename:"
   read filename

   # Check if the file exists
   if [ -e $filename ]; then
     echo "File $filename exists"
   else
     echo "File $filename does not exist"
   fi
   ```

3. **Simple Login Script**:
   ```bash
   #!/bin/bash

   # Define username and password
   correct_username="admin"
   correct_password="password123"

   # Prompt user for username and password
   echo "Enter username:"
   read username
   echo "Enter password:"
   read password

   # Check if the username and password are correct
   if [ "$username" == "$correct_username" ] && [ "$password" == "$correct_password" ]; then
     echo "Login successful"
   else
     echo "Invalid username or password"
   fi
   ```

4. **Check if a Number is Even or Odd**:
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

5. **Grade Calculation**:
   ```bash
   #!/bin/bash

   # Prompt user for a score
   echo "Enter your score (0-100):"
   read score

   # Determine the grade
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

#### Practice Problem Statements

1. **Check Leap Year**:
   - Write a script named `leapyear.sh` to check if a given year is a leap year.
   ```bash
   #!/bin/bash

   # Prompt user for a year
   echo "Enter a year:"
   read year

   # Check if the year is a leap year
   if [ $((year % 4)) -ne 0 ]; then
     echo "$year is not a leap year"
   elif [ $((year % 100)) -ne 0 ]; then
     echo "$year is a leap year"
   elif [ $((year % 400)) -ne 0 ]; then
     echo "$year is not a leap year"
   else
     echo "$year is a leap year"
   fi
   ```

2. **Number Comparison**:
   - Write a script named `compare.sh` to compare two numbers entered by the user.
   ```bash
   #!/bin/bash

   # Prompt user for two numbers
   echo "Enter first number:"
   read num1
   echo "Enter second number:"
   read num2

   # Compare the numbers
   if [ $num1 -gt $num2 ]; then
     echo "$num1 is greater than $num2"
   elif [ $num1 -lt $num2 ]; then
     echo "$num1 is less than $num2"
   else
     echo "$num1 is equal to $num2"
   fi
   ```

3. **Check String Length**:
   - Write a script named `strlen.sh` to check the length of a string entered by the user.
   ```bash
   #!/bin/bash

   # Prompt user for a string
   echo "Enter a string:"
   read str

   # Get the length of the string
   length=${#str}

   # Check the length of the string
   if [ $length -gt 10 ]; then
     echo "The string is longer than 10 characters"
   else
     echo "The string is 10 characters or shorter"
   fi
   ```

4. **Check Age Category**:
   - Write a script named `agecategory.sh` to determine the age category of a person based on their age.
   ```bash
   #!/bin/bash

   # Prompt user for their age
   echo "Enter your age:"
   read age

   # Determine the age category
   if [ $age -lt 13 ]; then
     echo "You are a child"
   elif [ $age -lt 20 ]; then
     echo "You are a teenager"
   elif [ $age -lt 65 ]; then
     echo "You are an adult"
   else
     echo "You are a senior"
   fi
   ```

5. **Day of the Week**:
   - Write a script named `dayofweek.sh` to determine the day of the week based on a number entered by the user (1-7).
   ```bash
   #!/bin/bash

   # Prompt user for a number (1-7)
   echo "Enter a number (1-7):"
   read num

   # Determine the day of the week
   if [ $num -eq 1 ]; then
     echo "Sunday"
   elif [ $num -eq 2 ]; then
     echo "Monday"
   elif [ $num -eq 3 ]; then
     echo "Tuesday"
   elif [ $num -eq 4 ]; then
     echo "Wednesday"
   elif [ $num -eq 5 ]; then
     echo "Thursday"
   elif [ $num -eq 6 ]; then
     echo "Friday"
   elif [ $num -eq 7 ]; then
     echo "Saturday"
   else
     echo "Invalid number"
   fi
   ```
