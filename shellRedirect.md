Shell I/O Redirection in Bash, covering the most commonly used commands and their options.

### I/O Redirection Basics

I/O redirection allows you to control where the input to a command comes from and where the output goes. There are three main file descriptors used for I/O redirection:

1. **Standard Input (stdin)**: File descriptor 0
2. **Standard Output (stdout)**: File descriptor 1
3. **Standard Error (stderr)**: File descriptor 2

### Redirecting Standard Output

#### Overwrite a file (`>`)
```sh
command > file
```
- Redirects the output of `command` to `file`, overwriting the file if it exists.

**Example:**
```sh
echo "Hello, World!" > output.txt
```
- Writes "Hello, World!" to `output.txt`. If `output.txt` exists, it will be overwritten.

#### Append to a file (`>>`)
```sh
command >> file
```
- Redirects the output of `command` to `file`, appending to the file if it exists.

**Example:**
```sh
echo "Another line" >> output.txt
```
- Appends "Another line" to `output.txt`.

### Redirecting Standard Input

#### Read from a file (`<`)
```sh
command < file
```
- Takes the input for `command` from `file`.

**Example:**
```sh
wc -l < input.txt
```
- Counts the number of lines in `input.txt`.

### Redirecting Standard Error

#### Redirect stderr to a file
```sh
command 2> file
```
- Redirects the standard error of `command` to `file`.

**Example:**
```sh
ls non_existent_file 2> error.log
```
- Writes the error message to `error.log` since `non_existent_file` does not exist.

#### Append stderr to a file
```sh
command 2>> file
```
- Redirects the standard error of `command` to `file`, appending if the file exists.

**Example:**
```sh
ls non_existent_file 2>> error.log
```
- Appends the error message to `error.log`.

### Redirecting Both stdout and stderr

#### Redirect stdout and stderr to the same file (`&>`)
```sh
command &> file
```
- Redirects both standard output and standard error to `file`.

**Example:**
```sh
ls existing_file non_existent_file &> output.log
```
- Writes both the output and the error message to `output.log`.

#### Append stdout and stderr to the same file (`&>>`)
```sh
command &>> file
```
- Redirects both standard output and standard error to `file`, appending if the file exists.

**Example:**
```sh
ls existing_file non_existent_file &>> output.log
```
- Appends both the output and the error message to `output.log`.

### Using Pipelines (`|`)

Pipelines allow you to use the output of one command as the input to another command.

**Example:**
```sh
ls -l | grep "txt"
```
- Lists all files in long format and then filters the list to show only those containing "txt".

### Combining Redirections

You can combine various types of redirections in a single command.

**Example:**
```sh
command > output.txt 2> error.txt
```
- Redirects stdout to `output.txt` and stderr to `error.txt`.

#### Redirecting stderr to stdout (`2>&1`)
```sh
command > file 2>&1
```
- Redirects both standard output and standard error to `file`.

**Example:**
```sh
ls existing_file non_existent_file > output.log 2>&1
```
- Writes both the output and the error message to `output.log`.

### Here Documents (`<<`)

Here documents allow you to provide input to commands directly within the script.

**Example:**
```sh
cat << EOF
This is line 1
This is line 2
EOF
```
- Sends the lines between `<< EOF` and `EOF` to the `cat` command.

### Practical Examples

#### Example 1: Counting Lines in a File
```sh
wc -l < input.txt > line_count.txt
```
- Counts the number of lines in `input.txt` and writes the result to `line_count.txt`.

#### Example 2: Redirecting Errors
```sh
grep "pattern" file.txt 2> errors.log
```
- Searches for "pattern" in `file.txt` and writes any error messages to `errors.log`.

#### Example 3: Combining stdout and stderr
```sh
find / -name "myfile" > results.log 2>&1
```
- Searches for `myfile` starting from the root directory and writes both the results and any errors to `results.log`.

#### Example 4: Using Pipelines
```sh
ps aux | grep "bash"
```
- Lists all running processes and filters to show only those containing "bash".

These commands and examples will help you understand and use I/O redirection effectively in Bash to control the flow of data in your scripts and commands.