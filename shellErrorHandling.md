### Shell Error Handling

Error handling in shell scripting is crucial for creating robust and reliable scripts. Proper error handling ensures that your scripts can handle unexpected situations gracefully and provide meaningful feedback to the user. Here, we'll cover various error-handling techniques, including theory and practical examples.

#### Theory

1. **Exit Status**
    - Every command in a shell script returns an exit status upon completion. An exit status of `0` indicates success, while any non-zero value indicates an error.
    - You can access the exit status of the last executed command using the special variable `$?`.

2. **`exit` Command**
    - The `exit` command is used to terminate a script and return a specific exit status to the calling process.
    - Syntax: `exit [n]`, where `n` is the exit status (default is `0`).

3. **`test` Command**
    - The `test` command evaluates expressions and returns an exit status (`0` for true, non-zero for false).
    - Common usage: `test expression`, `[ expression ]`, or `[[ expression ]]`.

4. **`set -e`**
    - The `set -e` command instructs the shell to exit immediately if any command returns a non-zero exit status.
    - Useful for making scripts fail fast on errors.

5. **`trap` Command**
    - The `trap` command captures signals and executes specified commands when the script receives those signals.
    - Common signals: `SIGINT` (interrupt), `SIGTERM` (terminate), `EXIT` (script exit).

6. **`||` and `&&` Operators**
    - `||`: Executes the next command only if the previous command fails.
    - `&&`: Executes the next command only if the previous command succeeds.

### Practical Examples

#### Example 1: Checking Exit Status

```sh
#!/bin/bash

# Run a command
ls /nonexistent_directory

# Check the exit status
if [ $? -ne 0 ]; then
    echo "Command failed"
else
    echo "Command succeeded"
fi
```

**Explanation:**
- The script tries to list a nonexistent directory.
- It checks the exit status of the `ls` command using `$?`.
- If the command fails (non-zero exit status), it prints "Command failed".

#### Example 2: Using `exit` Command

```sh
#!/bin/bash

# Check if a file exists
if [ ! -f "$1" ]; then
    echo "File not found!"
    exit 1  # Exit with status 1
fi

# Continue with the script if the file exists
echo "Processing file: $1"
```

**Explanation:**
- The script checks if a file (passed as an argument) exists.
- If the file doesn't exist, it prints an error message and exits with status `1`.
- If the file exists, it continues with the script.

#### Example 3: Using `set -e`

```sh
#!/bin/bash
set -e  # Exit immediately on error

# Run multiple commands
echo "Creating directory..."
mkdir /some/directory

echo "Changing to directory..."
cd /some/directory

echo "Creating file..."
touch file.txt

echo "All commands succeeded"
```

**Explanation:**
- The script uses `set -e` to exit immediately if any command fails.
- If any command fails, the script stops executing further commands.

#### Example 4: Using `trap` Command

```sh
#!/bin/bash

# Define a cleanup function
cleanup() {
    echo "Cleaning up..."
    rm -f /tmp/tempfile
}

# Set a trap for the EXIT signal
trap cleanup EXIT

# Create a temporary file
touch /tmp/tempfile
echo "Temporary file created"

# Simulate an error
false

echo "This message won't be printed"
```

**Explanation:**
- The script defines a `cleanup` function to remove a temporary file.
- It sets a trap for the `EXIT` signal to call the `cleanup` function when the script exits.
- The script creates a temporary file and simulates an error using `false`.
- The `cleanup` function is called automatically when the script exits.

#### Example 5: Using `||` and `&&` Operators

```sh
#!/bin/bash

# Use || to execute a command on failure
mkdir /some/directory || echo "Failed to create directory"

# Use && to execute a command on success
cd /some/directory && echo "Changed to directory"
```

**Explanation:**
- The script uses `||` to print a message if the `mkdir` command fails.
- It uses `&&` to print a message if the `cd` command succeeds.

#### Example 6: Using `test` Command

```sh
#!/bin/bash

# Define a function to check if a number is positive
is_positive() {
    if test $1 -gt 0; then
        return 0
    else
        return 1
    fi
}

# Check if a number is positive
number=-5
if is_positive $number; then
    echo "$number is positive"
else
    echo "$number is not positive"
fi
```

**Explanation:**
- The script defines a function `is_positive` that checks if a number is positive using the `test` command.
- It calls the function and prints a message based on the result.

### Summary

Proper error handling is essential for writing reliable shell scripts. By understanding and using exit statuses, the `exit` command, `set -e`, `trap`, and logical operators (`||` and `&&`), you can create scripts that handle errors gracefully and provide meaningful feedback. Practice these examples and incorporate error handling into your own scripts to improve their robustness. If you have any specific questions or need further assistance, feel free to ask!