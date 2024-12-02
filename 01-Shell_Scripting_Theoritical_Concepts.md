# Mastering Shell Scripting Fundamentals
This documentation introduces the fundamentals of **shell scripting**, **covering essential concepts**, **command** & **examples**. Learn how to automate tasks, manage systems & enhance productivity in Unix-based environments with variables, loops & functions.
<div align="center">
    <img src="Diagrams/Script-Logo.png" alt="Project Logo" width=30%>
</div>

# What is Linux Shell?
A Linux shell is a command-line interpreter that processes user commands and scripts, acting as an interface between the Applications and the Operating System. Examples include **`bash`**, **`sh`** & **`zsh`**.
<div align="center">
    <img src="Diagrams/Architecture.png" alt="Project Logo" width=40%>
</div>

# What is Shell Script?
A **shell script is a text file** containing a **sequence of shell commands**. It is executed by a shell interpreter like **`bash`**, **`sh`** or **`zsh`**.
# What is Shell Scripting?
Shell Scripting is the process of writing and creating shell scripts. It involves using shell syntax and commands to develop automation scripts that perform tasks on the system. It involves writing scripts using shell commands to perform a series of tasks.
# Use Cases of Shell Scripting
- **Automate Repetitive Tasks** - Save time by automating backups, installations & updates.
- **Simplify Commands** - Combine multiple commands into a single script.
- **System Administration** - Manage users, files & services efficiently.
- **Periodic Monitoring** - Automatically check system health regularly.
- **Alerts and Notifications** - Get alerts for issues like low disk space.
- **Troubleshooting and Audits** - Identify problems and maintain logs.
# Pre-Requisites 
- Linux Basics.
- Command Line Basics
- No Programming Knowledge Required.
# How to Check Shell Name?
Open a terminal on Linux and run
```bash
    echo $0
```
The Output will show the **`bash`** name of Current Linux Operating System.
# First Shell-Script
Here are the steps to create and run your first shell script from scratch :
## Step 1 : Create a Text Editor to Create a Script
```bash
    vim first-script.sh
```
## Step 2 : Write the Following Content Inside the File
```bash
    echo "Hi, I am Pritam"
    echo "This is my first script"
    pwd
    ls -l
```
Save & Exit.
## Step 3 : Make the Script Executable 
Change the script's permissions to make it executable
```bash
    chmod +x first-script.sh
```
## Step 4 : Run the Script
```bash
    ./first-script.sh
```
If everything is done correctly, the script should run and execute the commands within it.
## Step 5 : Check the Output
The output will be shown like this :
```bash
    Hi, I am Pritam
    This is my first script
    /home/username/my_first_script
    total 4
    -rwxr-xr-x 1 pritam pritam 66 Dec 1 15:28 first-script.sh
```
# Best Practice for Script Name
1. Give your Script a name that makes sense.
    - **Good Example** - `my-name`
    - **Bad Example** - `script.sh`; `myscript.sh`;`test.sh`
2. Leave out **`.sh`** extension for executables.
     - **Good Example** - `my-name`
    - **Bad Example** - `script.sh`; `myscript.sh`;`test.sh`

# Shebang(`#!`) for Shell Scripting
The shebang (**`#!`**) is the first line in a shell script that specifies the interpreter to execute the script. It tells the system which shell or interpreter to use for executing the script.
## Syntax 
```bash 
    #!/path/to/interpreter
```
The **`#!`** is followed by the Absolute Path of the interpreter.
## Examples 
### 1. Use **`which`** to find the interpreter's path 
```bash
    which bash
```
Or,
```bash
    which python3
```
### 2. Add the Path of Interpreter as Shebang to the Script
If you're using **`bash`** your script starts with :
```bash
    #!/bin/bash 
```
**`bash`** is default on most Linux Systems.

If using zsh, your script starts with :
```bash
    #!/bin/zsh
```
For Python
```bash
    #!/usr/bin/python3
```
### Example of a Python Script
```bash
    #!/usr/bin/python3
    # Python code to print a name
    print("Hi, I am Pritam")
```
**Note :** The script is saved with a **`.sh`** extension, but it behaves as a Python script due to the interpreter in the shebang.
## Why Shebang is Important?
1. Using which avoids hardcoding incorrect or unavailable paths.
2. The shebang ensures the script runs with the specified interpreter, even if another shell is active.
3. Makes the script portable across systems with the same interpreter.

# Built-Ins
- **Definition** - Commands integrated directly into the shell (e.g., **`bash`**, **`zsh`**)
- **Execution** - Run by the shell itself not external programs, making them faster.
- **Storage** - Part of the shell's binary (e.g., **`/bin/bash`** or **`/usr/bin/zsh`**) and do not exist as standalone files.
- **Examples**-
    - **`echo`** - Prints text to the terminal.
    - **`cd`** - Changes directories.
    - **`export`** - Sets environment variables.
    - **`alias`** - Creates shortcuts for commands.
# Keywords
- **Definition** - Reserved words with special meanings in shell scripting, used to define the structure of scripts.
- **Usage** - Cannot be used as variable names or redefined.
- **Storage** - Keywords are hardcoded in the shell's binary and are not standalone files.
- **Examples**-
    - **`if, else, fi`** - Used for conditional execution.
    - **`for, while, do, done`** - Loop control.
    - **`function`** - Defines a reusable block of code.
    - **`case, esac`** - Multi-condition branching.
# Commands
- **Definition** - Instructions that perform specific tasks, either built-in or external programs.
- **Types and Storage** -
    - **Internal Commands** - Built into the shell, stored within the shell binary.
    - **External Commands** - Executable files located in system directories.
- **Common Storage Locations** -
    - **`/bin`** - Essential binaries (e.g., **`ls`**, **`pwd`**, **`cp`**).
    - **`/usr/bin`** - Additional user binaries (e.g., **`grep`**, **`curl`**, **`vim`**).
    - **`/usr/local/bin`** - User-installed binaries.
- **Examples** -
    - **`ls`** - **`/bin/ls`** - Lists directory contents.
    - **`grep`** - **`/usr/bin/grep`** - Searches for patterns in text.
    - **`curl`** - **`/usr/bin/curl`** - Transfers data from or to a server.

# Print Hello Message is Different Color
"Hello, World!" in different colors using shell scripting :
```bash
    #!/bin/bash

    # Print "Hello, World!" in different colors
    echo -e "\033[31mHello, World! in Red\033[0m"
    echo -e "\033[32mHello, World! in Green\033[0m"
    echo -e "\e[33mHello, World! in Yellow\e[0m"
    echo -e "\e[34mHello, World! in Blue\e[0m"
    echo -e "\e[35mHello, World! in Magenta\e[0m"
    echo -e "\e[36mHello, World! in Cyan\e[0m"
```
## Explanation
1. **`\e`** -
- Represents the **`escape character`**.
- Equivalent to **`ESC`** in **ASCII**, which initiates an ANSI escape sequence.
- Can also be written as **`\033`**.
2. **`[Nm`** - 
- The code that specifies the desired formatting.
- **`N`** indicates the foreground color.
- **`m`** marks the end of the sequence and applies the effect.
## Color Codes for Foreground Text
- **`30`**	**Black**	\e[30mHello\e[0m
- **`31`**	**Red**	    \e[31mHello\e[0m
- **`32`**	**Green**	\e[32mHello\e[0m
- **`33`**	**Yellow**	\e[33mHello\e[0m
- **`34`**	**Blue**	\e[34mHello\e[0m
- **`35`**	**Magenta**	\e[35mHello\e[0m
- **`36`**	**Cyan**	\e[36mHello\e[0m
- **`37`**	**White**   \e[37mHello\e[0m