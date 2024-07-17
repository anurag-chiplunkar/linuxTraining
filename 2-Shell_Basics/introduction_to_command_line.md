
## Shell Basics

### Introduction to the Command Line

#### Theory
- **Command Line Interface (CLI)**: A text-based interface used to interact with the operating system. Users input commands that the system executes.
- **Shell**: A program that provides the command line interface. Common shells include `bash`, `zsh`, and `sh`.

#### Basic Command Line Usage

**Basic Commands:**
```bash
# Print working directory
pwd

# List files in the current directory
ls

# Change directory
cd /path/to/directory

# Display contents of a file
cat file.txt

# Create a new file
touch newfile.txt

# Remove a file
rm newfile.txt

# Create a new directory
mkdir newdirectory

# Remove a directory
rmdir newdirectory
```

**Command Syntax:**
- **Command**: The program or script you want to run.
- **Options**: Modifiers that change the behavior of the command (e.g., `-l` for `ls`).
- **Arguments**: The targets or inputs for the command (e.g., filenames or directories).

Example:
```bash
# List all files in long format in the /usr directory
ls -l /usr
```

**Combining Commands:**
- **Sequential Execution**: Use `;` to run multiple commands in sequence.
- **Conditional Execution**: Use `&&` to run the next command only if the previous one succeeded.
- **Alternative Execution**: Use `||` to run the next command only if the previous one failed.

Examples:
```bash
# Run two commands in sequence
echo "Hello" ; echo "World"

# Run the second command only if the first succeeds
mkdir newdir && cd newdir

# Run the second command only if the first fails
cd nonexistingdir || echo "Directory not found"
```

These notes and exercises should help you demonstrate the fundamentals of shell pipes and filters, environment variables, and command line usage. 
