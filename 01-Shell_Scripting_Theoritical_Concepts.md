# Mastering Shell Scripting Fundamentals
This documentation introduces the fundamentals of **shell scripting**, **covering essential concepts**, **command** & **examples**. Learn how to automate tasks, manage systems & enhance productivity in Unix-based environments with variables, loops & functions.
<div align="center">
    <img src="Diagrams/Script-Logo.png" alt="Project Logo" width=30%>
</div>

# What is Linux Shell?
A Linux shell is a command-line interpreter that processes user commands and scripts, acting as an interface between the user and the operating system. Examples include **`bash`**, **`sh`** & **`zsh`**.
<div align="center">
    <img src="Diagrams/Architecture.png" alt="Project Logo" width=40%>
</div>

# What is Shell Script?
A **shell script is a text file** containing a **sequence of shell commands**. It is executed by a shell interpreter like **`bash`**, **`sh`** or **`zsh`**.

# What is Shell Scripting?
Shell scripting is a powerful way to automate tasks and streamline processes in Unix-based systems like Linux. It involves writing scripts using shell commands to perform a series of tasks.


# Why Use Shell Scripting?
- **Automate Repetitive Tasks** - Save time by automating backups, installations, and updates.
- **Simplify Commands** - Combine multiple commands into a single script.
- **System Administration** - Manage users, files, and services efficiently.
- **Periodic Monitoring** - Automatically check system health regularly.
- **Alerts and Notifications** - Get alerts for issues like low disk space.
- **Troubleshooting and Audits** - Identify problems and maintain logs.
# Pre-Requisites 
- Linux Basics.
- Command Line Basics
- No Programming Knowledge Required.
# First Script Example
```bash
    # 1. Create a Directory named First-Script
    mkdir -p First-Script

    # 2. Create a .sh file inside the directory
    touch First-Script/hello-script.sh

    # 3. Add a script to print "Hello Pritam"
    echo 'echo "Hello Pritam"' > First-Script/hello-script.sh

    # Make the new script executable
    chmod +x First-Script/hello-script.sh

    # Run the script
    First-Script/hello_script.sh
```
## Explanation
- **Create a Directory** - **`mkdir -p First-Script`** creates the directory if it doesn’t already exist.
- **Create the .sh File** -  **`touch First-Script/hello-script.sh`** creates the script file inside the directory.
- **Add Script Content** - **`echo 'echo "Hello Pritam"' > First-Script/hello-script.sh`** writes the print command into the script.
- **Make It Executable** - **`chmod +x`** gives the script execution permissions.
- **Run the Script** - Finally, the script is executed with **`First-Script/hello-script.sh`**.

**Note**-The script will follow a serial order, executing each task in sequence, ensuring that each step is completed before moving to the next.
# Run Script as Command
## Step 1 : Write the Script
Create a script file named **`my-name`** without the **`.sh`**. Then write the following content :
```bash
    echo "Hello, This is Pritam!!"
```
## Step 2 : Make the Script Executable
Use the **`chmod`** command to make the script executable.
```bash
    chmod +x my-name
```
## Step 3 : Move the Script to a Directory in the `$PATH`
To run the script from anywhere, we need to place it in a directory that’s included in our **`$PATH`**. Common directories already in the **`$PATH`** include **`/usr/local/bin`** or **`/bin`**.
```bash
    sudo mv my-name /usr/local/bin/
```
## Step 4 : Command Execution
Now that our script is executable and located in a directory within our **`$PATH`**, we can run the script from any directory.
```bash
    myscript
```
If everything is done correctly, the script should run and execute the commands within it.
# Best Practice for Script Name
1. Give your Script a name that makes sense.
    - **Good Example** - `my-name`
    - **Bad Example** - `script.sh`; `myscript.sh`;`test.sh`
2. Leave out **`.sh`** extension for executables.
     - **Good Example** - `my-name`
    - **Bad Example** - `script.sh`; `myscript.sh`;`test.sh`
# Variables
A variable is a name used to store data or information. You can use it to hold values like text, numbers or commands, making your script dynamic and reusable.
## How to Define Variables?
- Variables are assigned using the **`=`** operator.
- No spaces are allowed around the **`=`**.
```bash
    variable_name=value
```
## Accessing Variables
- Use the **`$`** symbol to reference the variable.
- Enclose the variable name in **`{}`** if it’s part of a larger string.
```bash
    name="Pritam"
    echo "Hello, $name"
```
```output
    Hello, Pritam
```
## Key Types of Variables
### 1. Local Variables
- Define within a script or shell session.
- Exist only in the current context.
```bash
    message="Hello, World"
    echo $message
```
### 2. Environment Variables
- Predefined by the system (e.g., **`$HOME`**, **`$PATH`**).
- Accessible to child processes.
```bash
    echo "Your home directory is $HOME"
```
### 3. Special Variables
- Used for script arguments and system information.
- Examples:
    - **`$0`**: Name of the script.
    - **`$1`**, **`$2`**, ... : Positional parameters (arguments to the script).
    - **`$#`**: Number of arguments.
    - **`$?`**: Exit status of the last command.
```bash
    echo "Script Name: $0"
    echo "First Argument: $1"
```
### 4. Read-Only Variable
Once you defined a variable and don't want to change it untill end of the script. To make a variable constant, use **`readonly`**.
```bash
    readonly pi=3.1416
```
### Examples 
1. **Arithmetic with Variables**
```bash
    x=10
    y=5
    sum=$((x + y))
    echo "Sum: $sum"
```
### Best Practice for Variables
- Use meaningful names : `username`; `totalfiles`.
- Variable names must be in lower-case with underscores to separate words : `user_name`; `total_files`.

**Note** - Variables names are *Case Sensitive*.
