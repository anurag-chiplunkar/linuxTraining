
## Shell Basics

### Working with Files and Directories

#### Creating and Removing Files
- **Theory**: Use `touch` to create files and `rm` to remove them.
- **Usage**:
  - `touch [file]`: Create an empty file
  - `rm [file]`: Remove a file

**Hands-on Practice**:
```bash
# Create an empty file
touch newfile.txt

# Remove a file
rm newfile.txt
```

#### Moving and Renaming Files
- **Theory**: Use `mv` to move or rename files.
- **Usage**: `mv [source] [destination]`

**Hands-on Practice**:
```bash
# Move a file
mv file1.txt /path/to/destination/

# Rename a file
mv oldname.txt newname.txt
```

#### Copying Files and Directories
- **Theory**: Use `cp` to copy files and directories.
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

These notes and exercises should provide a comprehensive introduction to Unix shell basics.
