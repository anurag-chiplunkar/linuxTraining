### Scripting Fundamentals: Variables in Shell Scripts

#### Theory

**Variables in Shell Scripts**:
Variables are used to store data that can be referenced and manipulated within a script. They simplify code management and allow dynamic data handling.

**Declaring Variables**:
- Variables are declared without a `$` sign.
- Example: `name="John"`

**Using Variables**:
- Variables are referenced with a `$` sign.
- Example: `echo $name`

**Data Types**:
- **Strings**: Default data type, used to store text.
- **Integers**: Used to store numeric values.
- **Arrays**: Used to store multiple values in a single variable.

**Basic Rules**:
- No spaces around the `=` sign when declaring variables.
- Variable names should start with a letter or underscore and can contain alphanumeric characters and underscores.

**Example**:
```bash
#!/bin/bash

# Declare a variable
greeting="Hello, World!"

# Use the variable
echo $greeting
```

#### Example Scripts

1. **String Variable**:
   ```bash
   #!/bin/bash

   # Declare a string variable
   message="Hello, Shell Scripting!"

   # Use the variable
   echo $message
   ```

2. **Integer Variable**:
   ```bash
   #!/bin/bash

   # Declare integer variables
   num1=10
   num2=20

   # Perform arithmetic operations
   sum=$((num1 + num2))

   # Use the variable
   echo "The sum of $num1 and $num2 is $sum"
   ```

3. **Array Variable**:
   ```bash
   #!/bin/bash

   # Declare an array
   fruits=("Apple" "Banana" "Cherry")

   # Use the array elements
   echo "First fruit: ${fruits[0]}"
   echo "All fruits: ${fruits[@]}"
   ```

4. **Read User Input**:
   ```bash
   #!/bin/bash

   # Prompt user for input
   echo "Enter your name:"
   read name

   # Use the user input
   echo "Hello, $name!"
   ```

5. **Environment Variables**:
   ```bash
   #!/bin/bash

   # Use an environment variable
   echo "Home directory: $HOME"
   ```

#### Practice Problem Statements

1. **Temperature Conversion**:
   - Write a script named `tempconvert.sh` that converts a temperature from Celsius to Fahrenheit.
   ```bash
   #!/bin/bash

   # Prompt user for temperature in Celsius
   echo "Enter temperature in Celsius:"
   read celsius

   # Convert to Fahrenheit
   fahrenheit=$(( (celsius * 9/5) + 32 ))

   # Print the result
   echo "$celsius°C is equal to $fahrenheit°F"
   ```

2. **String Concatenation**:
   - Write a script named `concat.sh` that concatenates two strings entered by the user.
   ```bash
   #!/bin/bash

   # Prompt user for two strings
   echo "Enter first string:"
   read str1
   echo "Enter second string:"
   read str2

   # Concatenate the strings
   result="$str1 $str2"

   # Print the result
   echo "Concatenated string: $result"
   ```

3. **Array Manipulation**:
   - Write a script named `arraymanip.sh` that adds and removes elements from an array.
   ```bash
   #!/bin/bash

   # Declare an array
   colors=("Red" "Green" "Blue")

   # Add an element
   colors+=("Yellow")

   # Remove an element (Green)
   unset colors[1]

   # Print the array
   echo "Colors: ${colors[@]}"
   ```

4. **Simple Calculator**:
   - Write a script named `calculator.sh` that performs basic arithmetic operations based on user input.
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

   # Print the results
   echo "Sum: $sum"
   echo "Difference: $diff"
   echo "Product: $prod"
   echo "Quotient: $quot"
   ```

5. **File Operations**:
   - Write a script named `fileops.sh` that creates a file, writes data to it, and then displays the content.
   ```bash
   #!/bin/bash

   # Declare a filename
   filename="testfile.txt"

   # Create a file and write data to it
   echo "This is a test file." > $filename

   # Append data to the file
   echo "Adding more data to the file." >> $filename

   # Display the file content
   cat $filename
   ```
