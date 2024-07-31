### Using Regular Expressions in Shell Scripts

Regular expressions (regex) are powerful tools for matching patterns in strings. In shell scripting, they are commonly used with tools like `grep`, `sed`, `awk`, and within `[[ ... ]]` expressions in `bash`. This tutorial covers the theory and practical examples of using regular expressions in shell scripts.

#### Theory

1. **Basic Syntax**
    - **Literal Characters**: Matches exact characters.
    - **Metacharacters**: Special characters with specific meanings:
        - `.`: Any single character except newline.
        - `*`: Zero or more of the preceding element.
        - `+`: One or more of the preceding element.
        - `?`: Zero or one of the preceding element.
        - `^`: Start of a line.
        - `$`: End of a line.
        - `[]`: Matches any one of the characters inside the brackets.
        - `|`: Alternation (OR operator).
        - `()`: Grouping.
        - `\`: Escape character.

2. **Character Classes**
    - `[abc]`: Matches any one of `a`, `b`, or `c`.
    - `[^abc]`: Matches any character except `a`, `b`, or `c`.
    - `[a-z]`: Matches any character from `a` to `z`.

3. **Predefined Character Classes**
    - `\d`: Digit.
    - `\D`: Non-digit.
    - `\w`: Word character (alphanumeric plus `_`).
    - `\W`: Non-word character.
    - `\s`: Whitespace.
    - `\S`: Non-whitespace.

4. **Quantifiers**
    - `{n}`: Exactly `n` times.
    - `{n,}`: `n` or more times.
    - `{n,m}`: Between `n` and `m` times.

#### Practical Examples

##### Example 1: Using `grep` with Regular Expressions

`grep` is a command-line utility for searching plain-text data sets for lines that match a regular expression.

```sh
#!/bin/bash

# Search for lines containing "error" in a log file
grep "error" /var/log/syslog
```

**Explanation:**
- The script searches for lines containing the word "error" in `/var/log/syslog`.

##### Example 2: Using `grep` with Extended Regular Expressions

`grep` with the `-E` option (or `egrep`) allows using extended regular expressions.

```sh
#!/bin/bash

# Search for lines containing "error" or "fail" in a log file
grep -E "error|fail" /var/log/syslog
```

**Explanation:**
- The script searches for lines containing either "error" or "fail" in `/var/log/syslog`.

##### Example 3: Using `sed` for Substitution

`sed` is a stream editor for filtering and transforming text.

```sh
#!/bin/bash

# Replace all occurrences of "foo" with "bar" in a file
sed 's/foo/bar/g' input.txt > output.txt
```

**Explanation:**
- The script replaces all occurrences of "foo" with "bar" in `input.txt` and writes the output to `output.txt`.

##### Example 4: Using `awk` for Pattern Matching

`awk` is a programming language for pattern scanning and processing.

```sh
#!/bin/bash

# Print lines containing the word "pattern" in a file
awk '/pattern/ {print}' input.txt
```

**Explanation:**
- The script prints lines from `input.txt` that contain the word "pattern".

##### Example 5: Using Regular Expressions in `[[ ... ]]` Expressions

In `bash`, you can use regular expressions directly in `[[ ... ]]` expressions for conditional checks.

```sh
#!/bin/bash

# Check if a string matches a pattern
string="hello123"
if [[ $string =~ ^[a-z]+[0-9]+$ ]]; then
    echo "The string matches the pattern"
else
    echo "The string does not match the pattern"
fi
```

**Explanation:**
- The script checks if the string `hello123` matches the pattern `^[a-z]+[0-9]+$` (one or more letters followed by one or more digits).

##### Example 6: Using `grep` with Character Classes

```sh
#!/bin/bash

# Search for lines containing a digit
grep -E '[0-9]' file.txt
```

**Explanation:**
- The script searches for lines in `file.txt` that contain any digit.

##### Example 7: Using `grep` with Predefined Character Classes

```sh
#!/bin/bash

# Search for lines containing a word character
grep -P '\w' file.txt
```

**Explanation:**
- The script searches for lines in `file.txt` that contain any word character (alphanumeric or `_`).

##### Example 8: Using `sed` for Advanced Substitution

```sh
#!/bin/bash

# Replace only the first occurrence of "foo" with "bar" on each line
sed 's/foo/bar/' input.txt > output.txt
```

**Explanation:**
- The script replaces only the first occurrence of "foo" with "bar" on each line of `input.txt` and writes the output to `output.txt`.

### Summary

Regular expressions are powerful tools for matching and manipulating text in shell scripts. By mastering their syntax and usage with tools like `grep`, `sed`, and `awk`, you can perform complex text processing tasks efficiently. Practice these examples and experiment with your own patterns to become proficient in using regular expressions in your shell scripts. If you have any specific questions or need further assistance, feel free to ask!


### Processing Command-Line Arguments in Shell Scripts

Command-line arguments allow users to provide input to scripts when they run them. This tutorial covers the theory and practical examples of handling command-line arguments in shell scripts.

#### Theory

1. **Positional Parameters**
    - `$0`: The name of the script.
    - `$1`, `$2`, ... `$N`: The first, second, ..., Nth command-line arguments.
    - `$#`: The number of command-line arguments.
    - `$*`: All command-line arguments as a single string.
    - `$@`: All command-line arguments as separate strings.
    - `"$*"`: All command-line arguments as a single string, with arguments separated by the first character of the IFS variable.
    - `"$@"`: All command-line arguments as separate quoted strings.

2. **Shift Command**
    - `shift`: Shifts the positional parameters to the left.
    - `shift N`: Shifts the positional parameters to the left by `N` positions.

3. **Special Variables for Options**
    - `getopts`: A built-in command to parse command-line options.
    - Syntax: `getopts optstring varname`
        - `optstring`: A string containing the option characters to be recognized. If a character is followed by a colon (`:`), the option requires an argument.
        - `varname`: The variable name to store the option character.

### Practical Examples

#### Example 1: Basic Command-Line Arguments

```sh
#!/bin/bash

# Check if at least one argument is provided
if [ $# -eq 0 ]; then
    echo "No arguments provided."
    exit 1
fi

# Print the script name and the first three arguments
echo "Script name: $0"
echo "First argument: $1"
echo "Second argument: $2"
echo "Third argument: $3"
```

**Explanation:**
- The script checks if any arguments are provided. If not, it exits with an error message.
- It prints the script name and the first three command-line arguments.

#### Example 2: Using `$@` and `$*`

```sh
#!/bin/bash

# Print all arguments using $*
echo "All arguments using \$*: $*"

# Print all arguments using $@
echo "All arguments using \$@: $@"

# Print each argument separately using $@
for arg in "$@"; do
    echo "Argument: $arg"
done
```

**Explanation:**
- The script prints all arguments using `$*` and `$@`.
- It iterates over each argument separately using `$@`.

#### Example 3: Using `shift` Command

```sh
#!/bin/bash

# Print all arguments
echo "All arguments: $@"

# Shift the positional parameters
shift

# Print all arguments after shift
echo "All arguments after shift: $@"
```

**Explanation:**
- The script prints all arguments.
- It shifts the positional parameters to the left by one and prints the arguments again.

#### Example 4: Using `getopts` for Command-Line Options

```sh
#!/bin/bash

# Initialize variables
verbose=0
output_file=""

# Parse options
while getopts "vo:" opt; do
    case $opt in
        v)
            verbose=1
            ;;
        o)
            output_file=$OPTARG
            ;;
        *)
            echo "Invalid option: -$OPTARG"
            exit 1
            ;;
    esac
done

# Shift the processed options
shift $((OPTIND - 1))

# Print parsed options
echo "Verbose mode: $verbose"
echo "Output file: $output_file"
```

**Explanation:**
- The script uses `getopts` to parse the `-v` and `-o` options.
- `-v` sets the `verbose` variable to `1`.
- `-o` requires an argument, which is stored in the `output_file` variable.
- It shifts the processed options and prints the parsed values.

#### Example 5: Combining Positional Parameters and Options

```sh
#!/bin/bash

# Initialize variables
verbose=0
output_file=""

# Parse options
while getopts "vo:" opt; do
    case $opt in
        v)
            verbose=1
            ;;
        o)
            output_file=$OPTARG
            ;;
        *)
            echo "Invalid option: -$OPTARG"
            exit 1
            ;;
    esac
done

# Shift the processed options
shift $((OPTIND - 1))

# Print remaining arguments (positional parameters)
echo "Remaining arguments: $@"

# Print parsed options
echo "Verbose mode: $verbose"
echo "Output file: $output_file"
```

**Explanation:**
- The script parses options `-v` and `-o` as in the previous example.
- It shifts the processed options and prints the remaining arguments (positional parameters).

### Summary

Processing command-line arguments in shell scripts allows for flexible and user-friendly scripts. By using positional parameters, the `shift` command, and the `getopts` command for options, you can create powerful and versatile scripts. Practice these examples and experiment with different arguments and options to become proficient in handling command-line arguments in your shell scripts. If you have any specific questions or need further assistance, feel free to ask!