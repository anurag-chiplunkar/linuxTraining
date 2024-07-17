
## Shell Basics

### Environment Variables

#### Theory
- **Environment Variables**: Variables that are used to store information about the environment configuration. They are used by the shell and other programs to customize the execution environment.
- **Common Environment Variables**:
  - `PATH`: Directories to search for executable files
  - `HOME`: User's home directory
  - `USER`: Current logged-in user
  - `SHELL`: The shell being used

#### Manipulating Environment Variables

**Viewing Environment Variables:**
```bash
# Display all environment variables
printenv

# Display the value of a specific variable
echo $HOME
```

**Setting Environment Variables:**
```bash
# Set an environment variable
export MYVAR="myvalue"

# Verify the variable is set
echo $MYVAR
```

**Modifying the PATH:**
```bash
# Add a new directory to the PATH
export PATH=$PATH:/new/directory/path

# Verify the PATH is updated
echo $PATH
```

These notes and exercises should help you demonstrate the fundamentals of shell pipes and filters, environment variables, and command line usage. 
