
## Shell Basics

### Shell Pipes and Filters

#### Theory
- **Pipes (`|`)**: Pipes are used to pass the output of one command as input to another command.
- **Filters**: Filters are commands that take input, process it, and produce output. Common filters include `grep`, `sort`, `uniq`, `awk`, and `sed`.

#### Common Filters and Their Uses
- `grep`: Searches for patterns in text.
- `sort`: Sorts lines of text.
- `uniq`: Removes duplicate lines.
- `awk`: A programming language used for pattern scanning and processing.
- `sed`: A stream editor used to perform basic text transformations.

#### Hands-on Practice

**Using Pipes:**
```bash
# List files, then pass the output to less for paging
ls -l | less

# Display the contents of a file, then search for a pattern using grep
cat file.txt | grep "pattern"
```

**Using Filters:**
```bash
# Search for a specific word in a file
grep "search_term" file.txt

# Sort the contents of a file
sort file.txt

# Remove duplicate lines from a file
sort file.txt | uniq

# Print the second column of a file (assuming space-separated values)
awk '{print $2}' file.txt

# Substitute 'old' with 'new' in a file and display the output
sed 's/old/new/g' file.txt
```
These notes and exercises should help you demonstrate the fundamentals of shell pipes and filters, environment variables, and command line usage.
