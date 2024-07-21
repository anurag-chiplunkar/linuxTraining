### Scripting Fundamentals: Creating a Shell Script

#### Theory

**Shell Script**:
A shell script is a text file containing a sequence of commands for a Unix-based operating system. It automates repetitive tasks and executes a series of commands in a shell.

**File Permission**:
For a shell script to be executable, it must have the correct file permissions. Specifically, it needs the execute permission.

**Shebang Line (`#!/bin/bash`)**:
The shebang line at the top of the script specifies the path to the interpreter that should be used to execute the script. For example, `#!/bin/bash` tells the system to use the Bash shell.

**Creating a Shell Script**:
1. **Create a New File**:
   ```bash
   nano myscript.sh
   ```
2. **Add the Shebang Line**:
   ```bash
   #!/bin/bash
   ```
3. **Make the Script Executable**:
   ```bash
   chmod +x myscript.sh
   ```
4. **Run the Script**:
   ```bash
   ./myscript.sh
   ```

#### Example Scripts

1. **Hello World Script**:
   ```bash
   #!/bin/bash
   echo "Hello, World!"
   ```
   **Steps**:
   - Create a file named `hello.sh`.
   - Add the shebang line and the echo command.
   - Make the script executable: `chmod +x hello.sh`.
   - Run the script: `./hello.sh`.

2. **Display Current Date and Time**:
   ```bash
   #!/bin/bash
   echo "Current date and time: $(date)"
   ```
   **Steps**:
   - Create a file named `datetime.sh`.
   - Add the shebang line and the echo command with date.
   - Make the script executable: `chmod +x datetime.sh`.
   - Run the script: `./datetime.sh`.

3. **List Files in Directory**:
   ```bash
   #!/bin/bash
   echo "Listing files in current directory:"
   ls
   ```
   **Steps**:
   - Create a file named `listfiles.sh`.
   - Add the shebang line and the commands to list files.
   - Make the script executable: `chmod +x listfiles.sh`.
   - Run the script: `./listfiles.sh`.

4. **Create and Navigate Directory**:
   ```bash
   #!/bin/bash
   mkdir mydirectory
   cd mydirectory
   echo "Now in $(pwd)"
   ```
   **Steps**:
   - Create a file named `createdir.sh`.
   - Add the shebang line and the commands to create and navigate a directory.
   - Make the script executable: `chmod +x createdir.sh`.
   - Run the script: `./createdir.sh`.

5. **Simple Arithmetic**:
   ```bash
   #!/bin/bash
   a=5
   b=10
   sum=$((a + b))
   echo "Sum of $a and $b is $sum"
   ```
   **Steps**:
   - Create a file named `arithmetic.sh`.
   - Add the shebang line and the commands to perform arithmetic.
   - Make the script executable: `chmod +x arithmetic.sh`.
   - Run the script: `./arithmetic.sh`.

#### Practice Problem Statements

1. **Greet User**:
   - Write a script named `greet.sh` that asks for the user's name and then greets them.
   ```bash
   #!/bin/bash
   echo "Enter your name:"
   read name
   echo "Hello, $name!"
   ```
   - **Steps**: 
     - Create the script with the shebang line.
     - Add commands to read user input and print a greeting.
     - Make it executable and run it.

2. **Backup Directory**:
   - Write a script named `backup.sh` that creates a backup of a directory specified by the user.
   ```bash
   #!/bin/bash
   echo "Enter directory to backup:"
   read dir
   cp -r $dir ${dir}_backup
   echo "Backup of $dir created as ${dir}_backup"
   ```
   - **Steps**:
     - Create the script with the shebang line.
     - Add commands to read the directory name and create a backup.
     - Make it executable and run it.

3. **Check File Existence**:
   - Write a script named `checkfile.sh` that checks if a file exists and displays an appropriate message.
   ```bash
   #!/bin/bash
   echo "Enter filename to check:"
   read filename
   if [ -e $filename ]; then
     echo "File $filename exists."
   else
     echo "File $filename does not exist."
   fi
   ```
   - **Steps**:
     - Create the script with the shebang line.
     - Add commands to check file existence and display a message.
     - Make it executable and run it.

4. **Disk Usage Report**:
   - Write a script named `diskusage.sh` that displays the disk usage of the current directory.
   ```bash
   #!/bin/bash
   du -sh .
   ```
   - **Steps**:
     - Create the script with the shebang line.
     - Add the command to display disk usage.
     - Make it executable and run it.

5. **Rename Files**:
   - Write a script named `renamefiles.sh` that renames all `.txt` files in the current directory to `.bak`.
   ```bash
   #!/bin/bash
   for file in *.txt; do
     mv "$file" "${file%.txt}.bak"
   done
   echo "All .txt files renamed to .bak"
   ```
   - **Steps**:
     - Create the script with the shebang line.
     - Add commands to rename files.
     - Make it executable and run it.
