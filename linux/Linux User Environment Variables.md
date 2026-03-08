

**Environment variables** are **dynamic key-value pairs** used by the system and applications to store configuration data.

They define:

- System behavior
    
- Program settings
    
- User preferences
    
- File locations
    

Example structure:

```
VARIABLE_NAME=value
```

Example:

```
HOME=/home/kali
```

---

# Why Environment Variables Are Important

Environment variables help Linux:

- Configure applications
    
- Store system settings
    
- Manage file paths
    
- Store credentials or API keys
    
- Make scripts portable
    

They make systems **flexible, secure, and customizable**.

---

# Common Environment Variables

|Variable|Purpose|
|---|---|
|PATH|Locations of executable programs|
|HOME|User home directory|
|USER|Current username|
|SHELL|Default shell|
|PS1|Command prompt format|

---

# Viewing Environment Variables

## Using env

```bash
env
```

Example output:

```
SHELL=/usr/bin/bash
HOME=/home/kali
USER=kali
PATH=/usr/local/bin:/usr/bin:/bin
```

---

## Using printenv

```bash
printenv
```

This also prints environment variables.

---

# Environment Variables Naming

Environment variables are usually written in **UPPERCASE**.

Examples:

```
PATH
HOME
SHELL
USER
```

---

# Filtering Specific Variables

Sometimes the list is very long.

Use **grep** to filter.

Example:

```bash
set | grep PATH
```

Output example:

```
PATH=/usr/local/bin:/usr/bin:/bin
```

---

# Understanding the PATH Variable

The **PATH variable** tells the shell **where to find executable commands**.

Example command:

```bash
ls
```

The shell searches for `ls` in directories listed in PATH.

Typical PATH value:

```
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

Directories are separated by:

```
:
```

---

# Viewing PATH

```bash
echo $PATH
```

Example:

```
/home/kali/.local/bin:/usr/local/bin:/usr/bin:/bin
```

The shell checks directories **from left to right**.

---

# Changing Environment Variables (Temporary)

Environment variables can be changed **for the current session only**.

Example with **PS1** (prompt variable):

```bash
PS1="\w\$ "
```

New prompt example:

```
~/Desktop$
```

Explanation:

|Symbol|Meaning|
|---|---|
|\w|current directory|
|$|$ prompt symbol|

---

# Adding Directory to PATH

Suppose you install a tool in:

```
/root/ncateam
```

To run it from anywhere, add it to PATH.

Command:

```bash
PATH=$PATH:/root/ncateam
```

Now check:

```bash
echo $PATH
```

Output example:

```
/usr/local/bin:/usr/bin:/bin:/root/ncateam
```

Now commands in `/root/ncateam` can run from anywhere.

---

# Common Beginner Mistake

Wrong command:

```bash
PATH=/root/ncateam
```

Problem:

You **overwrite the entire PATH**.

System commands like:

```
ls
cd
echo
```

may stop working.

Correct method:

```bash
PATH=$PATH:/root/ncateam
```

Always **append**, not replace.

---

# Creating User-Defined Variables

Users can create their own variables.

Example:

```bash
MY_TOOL_DIR="/root/my_tools"
```

Access variable:

```bash
echo $MY_TOOL_DIR
```

Output:

```
/root/my_tools
```

---

# Using User Variables in Commands

Instead of typing long paths:

```
cd /root/my_tools
```

Use variable:

```bash
cd $MY_TOOL_DIR
```

This saves time and avoids typing mistakes.

---

# Exporting Variables

Variables normally work **only in the current shell**.

To make them available to **child processes**, use:

```bash
export MY_TOOL_DIR
```

Example:

```bash
export MY_TOOL_DIR="/root/my_tools"
```

Now scripts and programs can access it.

---

# Making Variables Permanent

Temporary variables disappear when the terminal closes.

To make them permanent, add them to:

```
~/.bashrc
```

Example:

```bash
nano ~/.bashrc
```

Add line:

```
export MY_TOOL_DIR="/root/my_tools"
```

Save and reload:

```bash
source ~/.bashrc
```

Now the variable loads every time the terminal opens.

---

# Removing Variables

To delete a variable:

```bash
unset variable_name
```

Example:

```bash
unset message
```

---

# Example of Custom Variable

Create variable:

```bash
message="hello world"
```

Check it:

```bash
echo $message
```

Output:

```
hello world
```

Remove variable:

```bash
unset message
```

Now check again:

```bash
echo $message
```

No output appears.

---

# Practical Hacker Use Case

Environment variables help hackers:

- store tool directories
    
- manage script paths
    
- hide API keys
    
- simplify commands
    

Example:

```
export TOOLS="/opt/pentesting_tools"
cd $TOOLS
```

---

# Important Commands Summary

| Command          | Purpose                                    |
| ---------------- | ------------------------------------------ |
| env              | show environment variables                 |
| printenv         | display environment variables              |
| set              | list shell variables                       |
| echo $VAR        | show variable value                        |
| export           | make variable available to child processes |
| unset            | remove variable                            |
| source ~/.bashrc | reload configuration                       |

---

# Quick Memory Trick

```
env        → show variables
echo $VAR  → view variable
export     → share variable
unset      → delete variable
PATH       → command locations
```

---

If you want, I can also show you **5 extremely important environment variable tricks hackers use in Kali Linux (used in CTFs and privilege escalation)**.