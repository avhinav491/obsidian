Linux Structure  
Linux and Windows organize their file systems in different way then windows . Linux starts from a single root directory `/`, forming one tree-like structure. Windows uses separate drives like `C:\` or `D:\`, treating each as its own storage space.

System files are stored differently as well. In Linux, configuration files are in `/etc/`, and programs are in `/bin/`, `/usr/bin/`, and `/sbin/`. In Windows, system files are mainly in `C:\Windows\`, and applications are installed in `C:\Program Files\`.User data in Linux is kept in `/home/username/` (e.g., `/home/kali`), while Windows stores user files in `C:\Users\Username\`.

Linux treats devices (hard drives, USBs, etc.) as files in `/dev/`, while Windows manages devices through Device Manager and assigns drive letters. Overall, Linux uses a unified “everything is a file” structure, while Windows uses a drive-based, graphical approach.

## 

# Linux Commands 

## Whoami

The `whoami` command displays the username of the currently logged-in user. This is useful when working with multiple accounts or checking if you are logged in as the root (administrator) user or a regular user.

---

## Print Working Directory (pwd)

The `pwd` command shows your current location in the filesystem. It prints the full absolute path from the root directory (`/`) to your current directory. This helps you understand where you are while navigating.

---

## Echo

The `echo` command prints text or variables to the terminal. It is often used to display messages or output variable values.  
Example:  
`echo Hello World`

---

## ls Command

The `ls` command lists files and directories in the current directory. It is one of the most frequently used Linux commands.  
Common options:

- `ls -l` → detailed list (shows permissions, owner, size, date)
    
- `ls -a` → shows hidden files
    
- `ls -la` → detailed list including hidden files
    

---

## cat Command

The `cat` command (short for concatenate) is used to display the contents of a file. It can also combine multiple files or create files.  
Example:  
`cat file.txt`

---

## Create a File (GUI)

In a graphical environment, you can create a file by right-clicking inside a folder and selecting **New Document**, then naming the file. This method is simple for beginners who prefer a visual interface.

---

# Navigating the Linux Filesystem

## Absolute Path

An absolute path starts from the root directory (`/`) and shows the complete location of a file or folder.  
Example:  
`/home/kali/Documents/file.txt`

---

## Relative Path

A relative path starts from your current directory. It does not begin with `/`.  
Example:  
If you are inside `/home/kali`, you can access Documents using:  
`Documents/file.txt`

---

## Changing Directories with cd

The `cd` (change directory) command allows you to move between directories.  
Example:  
`cd Documents`

---

## Ascend to the Parent Directory

To move one level up in the directory structure, use:  
`cd ..`

---

# Getting Help

## Referencing Manual Pages with man

The `man` command opens the manual page for a command, providing detailed information about its usage and options.  
Example:  
`man ls`

You can exit the manual page by pressing `q`.

---

# Hidden Files

Files that begin with a dot (`.`) are hidden by default. These are usually configuration files.  
To view hidden files, use:  
`ls -a`

---

# Finding Stuff

## find Command

The `find` command searches for files and directories in a specified location based on name, type, or other criteria.  
Example:  
`find /home -name file.txt`

---

## locate Command

The `locate` command quickly searches for files using a pre-built database. It is faster than `find` but may not show very recent files unless the database is updated.  
Example:  
`locate file.txt`

---

## grep Command

The `grep` command searches for specific text within files. It is very useful for finding keywords inside large files.  
Example:  
`grep "password" file.txt`

---

# Finding Binaries

## Finding Binaries in the PATH with which

The `which` command shows the full path of a command’s executable file. This helps identify where a program is installed.  
Example:  
`which python`

---

# About Files

## Creating a File with cat

You can create a file using:  
`cat > file.txt`  
After typing the content, press `CTRL + D` to save and exit.

---

## File Creation with touch

The `touch` command creates an empty file quickly.  
Example:  
`touch file.txt`

---

## Creating Files with Text Editors

### Nano

`nano` is a simple terminal-based text editor.  
Example:  
`nano file.txt`

Common shortcuts:

- `CTRL + O` → Save
    
- `CTRL + X` → Exit
    

---

# Creating a Directory

Use the `mkdir` command to create a new directory (folder).  
Example:  
`mkdir newfolder`

---

# Copying Files and Folders

The `cp` command copies files and directories.

- Copy a file: `cp file.txt backup.txt`
    
- Copy a folder: `cp -r folder backup_folder`
    

The `-r` option is required to copy directories.

---

# Renaming Files and Folders

The `mv` command is used to rename or move files and directories.  
Example:  
`mv oldname.txt newname.txt`

---

# Removing Files and Directories

- Remove a file: `rm file.txt`
    
- Remove an empty directory: `rmdir folder`
    
- Remove a directory with contents: `rm -r folder`
    

Be careful when using `rm -r`, as deleted files cannot be easily recovered.