### Shell Script Fundamentals

Shell scripting is a powerful way to automate tasks, manage systems, and process data. This tutorial covers the basics of shell scripting, including creating scripts, using variables, control flow, and basic examples.

### Theory

#### What is a Shell Script?

A shell script is a text file containing a sequence of commands for a Unix-based shell to execute. Shell scripts can automate repetitive tasks, perform batch processing, and simplify complex workflows.

#### Advantages of Shell Scripting

- **Automation**: Automates repetitive tasks to save time and reduce errors.
- **Efficiency**: Executes multiple commands in a sequence without user intervention.
- **Portability**: Can run on any Unix-based system with minimal changes.
- **Flexibility**: Easily integrates with other tools and programming languages.

### Creating a Shell Script

#### 1. Creating a Shell Script File

A shell script file can be created using any text editor. The script file usually has a `.sh` extension.

**Example:**
```sh
nano myscript.sh
```

#### 2. Adding the Shebang Line

The first line of a shell script should be the shebang (`#!`) line, which tells the system which interpreter to use to execute the script.

**Example:**
```sh
#!/bin/bash
```

#### 3. Adding Commands to the Script

Add the commands you want the script to execute.

**Example:**
```sh
#!/bin/bash
echo "Hello, World!"
```

#### 4. Making the Script Executable

Make the script executable using the `chmod` command.

**Example:**
```sh
chmod +x myscript.sh
```

#### 5. Running the Script

Run the script by specifying its path.

**Example:**
```sh
./myscript.sh
```

### Basic Shell Script Components

#### 1. Variables

Variables store data that can be used and manipulated within a script.

**Declaring Variables:**
```sh
VARIABLE_NAME=value
```

**Example:**
```sh
#!/bin/bash
greeting="Hello, World!"
echo $greeting
```

#### 2. Comments

Comments are lines in the script that are not executed. They are used to add notes or explanations.

**Single-Line Comment:**
```sh
# This is a comment
```

**Multi-Line Comment:**
```sh
: '
This is a multi-line comment
Line 2
'
```

#### 3. User Input

Use the `read` command to get input from the user.

**Example:**
```sh
#!/bin/bash
echo "Enter your name:"
read name
echo "Hello, $name!"
```

#### 4. Control Flow Statements

Control flow statements allow you to make decisions and repeat actions.

##### Conditional Statements

**If Statement:**
```sh
if [ condition ]; then
    # commands
fi
```

**Example:**
```sh
#!/bin/bash
echo "Enter a number:"
read number
if [ $number -gt 10 ]; then
    echo "The number is greater than 10."
else
    echo "The number is 10 or less."
fi
```

##### Looping Statements

**For Loop:**
```sh
for var in list; do
    # commands
done
```

**Example:**
```sh
#!/bin/bash
for i in 1 2 3 4 5; do
    echo "Number: $i"
done
```

**While Loop:**
```sh
while [ condition ]; do
    # commands
done
```

**Example:**
```sh
#!/bin/bash
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    count=$((count + 1))
done
```

### Basic Examples

#### Example 1: A Simple Greeting Script

**Script:**
```sh
#!/bin/bash
echo "Enter your name:"
read name
echo "Hello, $name!"
```

**Explanation:**
- `echo "Enter your name:"`: Displays a prompt for the user to enter their name.
- `read name`: Reads the input from the user and stores it in the variable `name`.
- `echo "Hello, $name!"`: Displays a greeting message with the user's name.

#### Example 2: Checking File Existence

**Script:**
```sh
#!/bin/bash
echo "Enter the filename:"
read filename
if [ -e $filename ]; then
    echo "File exists."
else
    echo "File does not exist."
fi
```

**Explanation:**
- `if [ -e $filename ]; then`: Checks if the file exists.
- `echo "File exists."`: Displays a message if the file exists.
- `echo "File does not exist."`: Displays a message if the file does not exist.

#### Example 3: Summing Numbers

**Script:**
```sh
#!/bin/bash
sum=0
for i in 1 2 3 4 5; do
    sum=$((sum + i))
done
echo "Sum: $sum"
```

**Explanation:**
- `sum=0`: Initializes the `sum` variable to 0.
- `for i in 1 2 3 4 5; do`: Loops through the numbers 1 to 5.
- `sum=$((sum + i))`: Adds the current number to the `sum` variable.
- `echo "Sum: $sum"`: Displays the total sum.

### Advanced Topics

#### Functions

Functions allow you to group commands and reuse them in your script.

**Defining a Function:**
```sh
function_name() {
    # commands
}
```

**Example:**
```sh
#!/bin/bash
greet() {
    echo "Hello, $1!"
}

greet "Alice"
greet "Bob"
```

**Explanation:**
- `greet() { ... }`: Defines a function named `greet`.
- `greet "Alice"`: Calls the `greet` function with "Alice" as an argument.

#### Error Handling

Use conditional statements to handle errors and exit the script if necessary.

**Example:**
```sh
#!/bin/bash
echo "Enter the filename:"
read filename
if [ ! -e $filename ]; then
    echo "File does not exist."
    exit 1
fi
echo "File exists."
```

**Explanation:**
- `if [ ! -e $filename ]; then`: Checks if the file does not exist.
- `exit 1`: Exits the script with an error code.

### Summary

- **Creating Scripts**: Create a text file with a `.sh` extension, add the shebang line, and make it executable.
- **Variables**: Store and manipulate data within the script.
- **Control Flow**: Use conditional statements and loops to control the execution of commands.
- **User Input**: Use the `read` command to get input from the user.
- **Functions**: Group and reuse commands using functions.
- **Error Handling**: Use conditional statements to handle errors and exit the script if necessary.

By mastering these fundamentals, you can create powerful and flexible shell scripts to automate tasks and manage systems effectively.