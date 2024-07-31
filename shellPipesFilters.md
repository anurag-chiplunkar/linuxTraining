### Bash Pipes and Filters Tutorial

Pipes and filters are powerful tools in Bash that allow you to process and manipulate data by chaining commands together. Pipes (`|`) connect the output of one command to the input of another, while filters are commands that process the input data and produce output.

### Theory

- **Pipes (`|`)**: The pipe symbol connects the output of one command directly to the input of another. This allows for the creation of complex command sequences without the need for intermediate files.
- **Filters**: Filters are commands that take input, process it, and produce output. Common filters include `grep`, `sort`, `uniq`, `awk`, `sed`, and `wc`.

### Basic Usage

#### Pipes
```sh
command1 | command2
```
- The output of `command1` becomes the input of `command2`.

**Example:**
```sh
ls -l | grep "txt"
```
- Lists files in long format and filters to show only those containing "txt".

### Common Filters

#### `grep` - Global Regular Expression Print

`grep` searches for patterns within text.

**Basic Usage:**
```sh
grep "pattern" file
```

**Example:**
```sh
ls -l | grep "txt"
```
- Filters the output of `ls -l` to show only lines containing "txt".

**Common Options:**
```sh
grep -i "pattern" file
```
- Case-insensitive search.

```sh
grep -v "pattern" file
```
- Invert match, showing lines that do not contain the pattern.

```sh
grep -r "pattern" directory
```
- Recursively search for the pattern in the directory.

#### `sort` - Sort Lines of Text

`sort` sorts lines of text.

**Basic Usage:**
```sh
sort file
```

**Example:**
```sh
ls | sort
```
- Lists files and directories and sorts them alphabetically.

**Common Options:**
```sh
sort -r file
```
- Sorts in reverse order.

```sh
sort -n file
```
- Sorts numerically.

#### `uniq` - Report or Omit Repeated Lines

`uniq` removes or reports repeated lines.

**Basic Usage:**
```sh
uniq file
```

**Example:**
```sh
sort file | uniq
```
- Sorts the lines in the file and removes duplicates.

**Common Options:**
```sh
uniq -c file
```
- Counts the occurrences of each line.

```sh
uniq -d file
```
- Displays only duplicate lines.

#### `wc` - Word, Line, Character, and Byte Count

`wc` counts words, lines, characters, and bytes.

**Basic Usage:**
```sh
wc file
```

**Example:**
```sh
ls | wc -l
```
- Counts the number of files and directories in the current directory.

**Common Options:**
```sh
wc -l file
```
- Counts the number of lines.

```sh
wc -w file
```
- Counts the number of words.

#### `head` and `tail` - Output the First/Last Part of Files

`head` displays the beginning, and `tail` displays the end of a file.

**Basic Usage:**
```sh
head file
tail file
```

**Example:**
```sh
ls -l | head -n 5
```
- Lists the first five lines of the detailed file listing.

```sh
ls -l | tail -n 5
```
- Lists the last five lines of the detailed file listing.

**Common Options:**
```sh
head -n 10 file
```
- Displays the first 10 lines of the file.

```sh
tail -n 10 file
```
- Displays the last 10 lines of the file.

#### `awk` - Pattern Scanning and Processing Language

`awk` processes and analyzes text files.

**Basic Usage:**
```sh
awk 'pattern {action}' file
```

**Example:**
```sh
ls -l | awk '{print $9}'
```
- Prints the names of files and directories from the detailed listing.

#### `sed` - Stream Editor

`sed` edits text in a stream or file.

**Basic Usage:**
```sh
sed 's/pattern/replacement/' file
```

**Example:**
```sh
echo "Hello World" | sed 's/World/Universe/'
```
- Replaces "World" with "Universe" in the input text.

### Practical Examples

#### Example 1: Using Pipes and Filters to Process Data

1. **List all files, filter by name, and count them:**
   ```sh
   ls -1 | grep "txt" | wc -l
   ```
   - Lists all files, filters for those containing "txt", and counts them.

2. **Sort and remove duplicates:**
   ```sh
   cat file.txt | sort | uniq
   ```
   - Reads `file.txt`, sorts the lines, and removes duplicates.

3. **Search for a pattern in multiple files and display the line numbers:**
   ```sh
   grep -rn "pattern" *
   ```
   - Recursively searches for "pattern" in all files and displays line numbers.

4. **Extract specific columns from a command output:**
   ```sh
   ps aux | awk '{print $1, $2, $11}'
   ```
   - Displays the user, process ID, and command name of all running processes.

5. **Replace text in a file and save the result:**
   ```sh
   sed 's/old/new/g' input.txt > output.txt
   ```
   - Replaces all occurrences of "old" with "new" in `input.txt` and saves the result to `output.txt`.

### Summary

- **Pipes**: Connect the output of one command to the input of another using `|`.
- **Filters**: Commands that process input and produce output, such as `grep`, `sort`, `uniq`, `wc`, `head`, `tail`, `awk`, and `sed`.

By mastering pipes and filters, you can perform complex data processing tasks efficiently and effectively in Bash.