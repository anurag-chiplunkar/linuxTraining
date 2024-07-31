### Shell Environment Variables Tutorial

Environment variables are dynamic values that affect the processes or programs on a computer. They exist in every operating system but are particularly significant in Unix-like systems and scripting environments such as Bash. Environment variables can be used to configure the behavior of software, store information about the system, and facilitate communication between processes.

### Basics of Environment Variables

#### Viewing Environment Variables

To view the current environment variables, you can use the `printenv` or `env` command:

```sh
printenv
```
- Displays all environment variables.

```sh
env
```
- Displays all environment variables.

To view a specific environment variable, use `echo`:

```sh
echo $VARIABLE_NAME
```
- Displays the value of `VARIABLE_NAME`.

**Example:**
```sh
echo $HOME
```
- Displays the home directory of the current user.

#### Setting Environment Variables

Environment variables can be set temporarily for the duration of a session or permanently by adding them to a configuration file.

##### Temporary Setting
```sh
VARIABLE_NAME=value
export VARIABLE_NAME
```
- Sets the value of `VARIABLE_NAME` and exports it so that it is available to child processes.

**Example:**
```sh
MY_VAR="Hello, World!"
export MY_VAR
echo $MY_VAR
```
- Sets and exports `MY_VAR`, then displays its value.

##### Permanent Setting

To set an environment variable permanently, add it to your shell's configuration file, such as `~/.bashrc` or `~/.bash_profile`.

**Example:**
1. Open `~/.bashrc` in a text editor:
   ```sh
   nano ~/.bashrc
   ```

2. Add the following line to set and export the variable:
   ```sh
   export MY_VAR="Hello, World!"
   ```

3. Save the file and reload the configuration:
   ```sh
   source ~/.bashrc
   ```

#### Unsetting Environment Variables

To remove an environment variable, use the `unset` command:

```sh
unset VARIABLE_NAME
```

**Example:**
```sh
unset MY_VAR
```
- Removes `MY_VAR` from the environment.

### Common Environment Variables

- `PATH`: A list of directories where the shell looks for executable files.
- `HOME`: The home directory of the current user.
- `USER`: The username of the current user.
- `SHELL`: The path to the current user's shell.
- `PWD`: The current working directory.
- `LANG`: The language setting for the system.
- `TERM`: The type of terminal to emulate when running the shell.

### Practical Examples

#### Example 1: Modifying `PATH`

The `PATH` variable is crucial because it determines where the shell looks for commands. You can add a directory to `PATH` to make its executables accessible from anywhere.

```sh
export PATH=$PATH:/new/directory
```

**Example:**
```sh
export PATH=$PATH:/usr/local/my_program/bin
```
- Adds `/usr/local/my_program/bin` to the `PATH` variable.

#### Example 2: Using Environment Variables in Scripts

Environment variables can be used within scripts to make them more flexible and portable.

**Example Script:**
```sh
#!/bin/bash

echo "Current user: $USER"
echo "Home directory: $HOME"
echo "Current shell: $SHELL"
```

Save the script as `env_script.sh`, make it executable, and run it:

```sh
chmod +x env_script.sh
./env_script.sh
```

**Output:**
```
Current user: your_username
Home directory: /home/your_username
Current shell: /bin/bash
```

#### Example 3: Setting Variables for a Single Command

You can set environment variables for a single command without modifying the environment permanently.

```sh
VARIABLE_NAME=value command
```

**Example:**
```sh
MY_VAR="Hello" echo $MY_VAR
```
- Sets `MY_VAR` to "Hello" only for the `echo` command.

**Output:**
```
Hello
```

#### Example 4: Using `env` to Run a Command with Modified Environment

The `env` command can be used to run a command with a modified environment.

```sh
env VARIABLE_NAME=value command
```

**Example:**
```sh
env MY_VAR="Hello" bash -c 'echo $MY_VAR'
```
- Runs a new Bash shell with `MY_VAR` set to "Hello".

**Output:**
```
Hello
```

### Exporting Variables

The `export` command makes a variable available to child processes.

**Example:**
```sh
MY_VAR="Hello"
export MY_VAR
bash -c 'echo $MY_VAR'
```
- Exports `MY_VAR` so that it is available in the child Bash process.

**Output:**
```
Hello
```

### Removing Variables from the Environment

You can use the `unset` command to remove environment variables.

**Example:**
```sh
unset MY_VAR
echo $MY_VAR
```
- Removes `MY_VAR` and attempts to display its value (which will be empty).

**Output:**

### Special Variables

Bash also includes a number of special variables:

- `$?`: The exit status of the last command.
- `$$`: The process ID of the current shell.
- `$!`: The process ID of the last background command.
- `$0`: The name of the script or shell.
- `$1`, `$2`, ...: Positional parameters for command-line arguments.

**Example:**
```sh
#!/bin/bash

echo "Script name: $0"
echo "First argument: $1"
echo "Second argument: $2"
```

Save the script as `args_script.sh`, make it executable, and run it with arguments:

```sh
chmod +x args_script.sh
./args_script.sh arg1 arg2
```

**Output:**
```
Script name: ./args_script.sh
First argument: arg1
Second argument: arg2
```

### Summary

Environment variables are essential for configuring the behavior of the shell and the programs that run within it. By understanding how to view, set, and use these variables, you can create more flexible and powerful scripts and command-line operations.