
## Shell Basics

### 1. Common Shell Commands

#### `ls` - List directory contents
- **Theory**: Lists files and directories in the current directory.
- **Options**:
  - `ls -l`: Long listing format
  - `ls -a`: Show all files, including hidden files
  - `ls -lh`: Long listing with human-readable file sizes

**Hands-on Practice**:
```bash
# List all files and directories in the current directory
ls

# List all files and directories, including hidden ones
ls -a

# List files in long format
ls -l

# List files in long format with human-readable sizes
ls -lh
```

#### `cd` - Change directory
- **Theory**: Changes the current directory to the specified directory.
- **Usage**: `cd [directory]`
- **Examples**:
  - `cd /home/user`: Change to the `/home/user` directory
  - `cd ..`: Move up one directory level

**Hands-on Practice**:
```bash
# Change to the home directory
cd ~

# Change to the /usr directory
cd /usr

# Move up one directory level
cd ..
```

#### `pwd` - Print working directory
- **Theory**: Displays the current directory path.
- **Usage**: `pwd`

**Hands-on Practice**:
```bash
# Print the current directory
pwd
```

#### `mkdir` - Make directories
- **Theory**: Creates a new directory.
- **Usage**: `mkdir [directory]`
- **Options**:
  - `mkdir -p [path]`: Create intermediate directories as needed

**Hands-on Practice**:
```bash
# Create a new directory called test
mkdir test

# Create nested directories
mkdir -p dir1/dir2/dir3
```

#### `rm` - Remove files or directories
- **Theory**: Deletes files or directories.
- **Usage**: `rm [file]`
- **Options**:
  - `rm -r [directory]`: Remove directories and their contents recursively
  - `rm -f [file]`: Force removal without prompting

**Hands-on Practice**:
```bash
# Remove a file called file.txt
rm file.txt

# Remove a directory and its contents
rm -r dir1

# Force remove a file
rm -f file.txt
```

#### `cp` - Copy files or directories
- **Theory**: Copies files or directories.
- **Usage**: `cp [source] [destination]`
- **Options**:
  - `cp -r [source] [destination]`: Copy directories recursively

**Hands-on Practice**:
```bash
# Copy a file
cp file1.txt file2.txt

# Copy a directory
cp -r dir1 dir2
```

#### `mv` - Move or rename files or directories
- **Theory**: Moves or renames files or directories.
- **Usage**: `mv [source] [destination]`

**Hands-on Practice**:
```bash
# Move a file to a different directory
mv file1.txt /path/to/destination/

# Rename a file
mv oldname.txt newname.txt
```

#### `cat` - Concatenate and display files
- **Theory**: Displays the contents of a file.
- **Usage**: `cat [file]`

**Hands-on Practice**:
```bash
# Display the contents of a file
cat file1.txt

# Concatenate multiple files and display
cat file1.txt file2.txt
```

#### `more` - View file contents interactively
- **Theory**: Displays file contents one screen at a time.
- **Usage**: `more [file]`

**Hands-on Practice**:
```bash
# View a file with more
more file1.txt
```

#### `less` - View file contents interactively
- **Theory**: Similar to `more`, but allows backward movement in the file.
- **Usage**: `less [file]`

**Hands-on Practice**:
```bash
# View a file with less
less file1.txt
```

#### `man` - Display manual pages
- **Theory**: Provides an interface to the system reference manuals.
- **Usage**: `man [command]`

**Hands-on Practice**:
```bash
# View the manual for the ls command
man ls
```

These notes and exercises should provide a comprehensive introduction to Unix shell basics.
