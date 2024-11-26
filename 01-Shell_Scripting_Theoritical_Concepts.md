# Mastering Shell Scripting Fundamentals
This documentation introduces the fundamentals of shell scripting, covering essential concepts, command & examples. Learn how to automate tasks, manage systems & enhance productivity in Unix-based environments with variables, loops & functions.
## What is Shell Script?
A shell script is a text file containing a sequence of shell commands. It is executed by a shell interpreter like **`bash`**, **`sh`** or **`zsh`**.
<div align="center">
    <img src="Diagrams/Shell-Script-Logo.png" alt="Project Logo" width=50%>
</div>

## What is Shell Scripting?
Shell scripting is a powerful way to automate tasks and streamline processes in Unix-based systems like Linux. It involves writing scripts using shell commands to perform a series of tasks.
## Why Use Shell Scripting?
- **Automate Repetitive Tasks** - Save time by automating backups, installations, and updates.
- **Simplify Commands** - Combine multiple commands into a single script.
- **System Administration** - Manage users, files, and services efficiently.
- **Periodic Monitoring** - Automatically check system health regularly.
- **Alerts and Notifications** - Get alerts for issues like low disk space.
- **Troubleshooting and Audits** - Identify problems and maintain logs.
## Pre-Requisites 
- Linux Basics.
- Command Line Basics
- No Programming Knowledge Required.
## First Script Example
```bash
    # 1. Create a Directory named First-Script
    mkdir -p First-Script

    # 2. Create a .sh file inside the directory
    touch First-Script/hello_script.sh

    # 3. Add a script to print "Hello Pritam"
    echo 'echo "Hello Pritam"' > First-Script/hello_script.sh

    # Make the new script executable
    chmod +x First-Script/hello_script.sh

    # Run the script
    First-Script/hello_script.sh
```
### Explanation
- **Create a Directory** - **`mkdir -p First-Script`** creates the directory if it doesn’t already exist.
- **Create the .sh File** -  **`touch First-Script/hello_script.sh`** creates the script file inside the directory.
- **Add Script Content** - **`echo 'echo "Hello Pritam"' > First-Script/hello_script.sh`** writes the print command into the script.
- **Make It Executable** - **`chmod +x`** gives the script execution permissions.
- **Run the Script** - Finally, the script is executed with **`First-Script/hello_script.sh`**.

**Note**-The script will follow a serial order, executing each task in sequence, ensuring that each step is completed before moving to the next.