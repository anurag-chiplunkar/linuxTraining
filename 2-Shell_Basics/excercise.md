
### Environment Variables

1. **Viewing and Setting Environment Variables**:
   ```bash
   # Display the current value of the PATH variable
   echo $PATH

   # Set a new environment variable MYVAR and display its value
   export MYVAR="HelloWorld"
   echo $MYVAR
   ```

2. **Modifying the PATH**:
   ```bash
   # Add /usr/local/bin to the PATH and verify the change
   export PATH=$PATH:/usr/local/bin
   echo $PATH
   ```

3. **Using an Environment Variable in a Command**:
   ```bash
   # Set a variable and use it in a command
   export DIRNAME="mydirectory"
   mkdir $DIRNAME
   ls -l $DIRNAME
   ```

4. **Persisting Environment Variables**:
   ```bash
   # Add an environment variable to .bashrc or .bash_profile to make it persistent
   echo 'export MYVAR="PersistentValue"' >> ~/.bashrc
   source ~/.bashrc
   echo $MYVAR
   ```

5. **Removing an Environment Variable**:
   ```bash
   # Set and then unset an environment variable
   export TEMPVAR="tempvalue"
   echo $TEMPVAR
   unset TEMPVAR
   echo $TEMPVAR  # This should be empty
   ```

### Shell Pipes and Filters

1. **Using `grep` with Pipes**:
   ```bash
   # Search for the word "error" in the output of a log file
   cat /var/log/syslog | grep "error"
   ```

2. **Sorting and Removing Duplicates**:
   ```bash
   # Sort the contents of a file and remove duplicates
   sort names.txt | uniq
   ```

3. **Filtering with `awk`**:
   ```bash
   # Print the second column of a space-separated file
   awk '{print $2}' data.txt
   ```

4. **Substituting Text with `sed`**:
   ```bash
   # Replace all instances of "foo" with "bar" in a file and display the result
   cat input.txt | sed 's/foo/bar/g'
   ```

5. **Chaining Multiple Commands**:
   ```bash
   # List files in long format, filter by user 'root', and display the result page by page
   ls -l /etc | grep "root" | less
   ```

### Shell I/O Redirection

1. **Redirecting Output to a File**:
   ```bash
   # Redirect the output of ls to a file called filelist.txt
   ls > filelist.txt
   ```

2. **Appending Output to a File**:
   ```bash
   # Append the date to a file called log.txt
   date >> log.txt
   ```

3. **Using Input Redirection**:
   ```bash
   # Use the contents of input.txt as input to the cat command
   cat < input.txt
   ```

4. **Combining Output Redirection and Pipes**:
   ```bash
   # Redirect the sorted list of files to sorted_files.txt and count the lines in the file
   ls | sort > sorted_files.txt
   wc -l < sorted_files.txt
   ```

5. **Using a Pipe with a Redirected Command**:
   ```bash
   # Count the number of lines containing "search_term" in file.txt and redirect the count to count.txt
   grep "search_term" file.txt | wc -l > count.txt
   ```

These examples should provide a good range of practical exercises for environment variables, shell pipes and filters, and shell I/O redirection.
