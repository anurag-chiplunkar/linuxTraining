
## Shell Basics

### Shell I/O Redirection

#### Output Redirection (`>`, `>>`)
- **Theory**: Redirect the output of a command to a file.
- **Usage**:
  - `command > file`: Redirect output to a file (overwrite)
  - `command >> file`: Redirect output to a file (append)

**Hands-on Practice**:
```bash
# Redirect the output of ls to a file
ls > output.txt

# Append the output of ls to a file
ls >> output.txt
```

#### Input Redirection (`<`)
- **Theory**: Use a file as input to a command.
- **Usage**: `command < file`

**Hands-on Practice**:
```bash
# Use a file as input to a command
cat < input.txt
```

#### Pipe (`|`)
- **Theory**: Pass the output of one command as input to another command.
- **Usage**: `command1 | command2`

**Hands-on Practice**:
```bash
# Pipe the output of ls to less
ls -l | less

# Pipe the output of cat to grep
cat file1.txt | grep "search_term"
```

These notes and exercises should provide a comprehensive introduction to Unix shell basics.
