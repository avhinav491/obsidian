

Software management in Linux involves **installing, updating, searching, and removing software packages**. During tasks like **system administration or penetration testing**, users frequently install and manage different tools.

Linux uses **package managers** such as:

- **APT** – Debian-based systems (Ubuntu, Kali)
    
- **DNF/YUM** – Fedora, CentOS
    
- **Pacman** – Arch Linux
    
- **dpkg** – Low-level Debian package manager
    
- **pip** – Python package manager
    
- **git** – Used to download software from repositories like GitHub
    

---

# What is a Repository?

A **repository** is a **storage location where software packages are stored and maintained**.

It contains:

- Software packages
    
- Metadata
    
- Dependency information
    

Repositories allow users to **download and install software easily**.

### Types of Linux Repositories

|Repository Type|Used By|
|---|---|
|APT|Debian, Ubuntu, Kali|
|YUM / DNF|Fedora, CentOS|
|Pacman|Arch Linux|
|Snap / Flatpak|Universal packages|

Repositories ensure **secure and organized software distribution**.

---

# APT (Advanced Package Tool)

APT is the **package management system used in Debian-based distributions** such as **Ubuntu and Kali Linux**.

It manages **`.deb` packages** and automatically handles dependencies.

### Repository Configuration File

```
/etc/apt/sources.list
```

APT tools include:

- `apt`
    
- `apt-get`
    
- `apt-cache`
    

---

# Locating a Package

Before installing software, you can **search the repository** to check if the package exists.

### Using apt-cache

```
apt-cache search nginx
```

### Using apt

```
apt search nginx
```

These commands search the **APT cache database** and show available packages.

---

# Updating and Upgrading Packages

Two important commands keep your system updated.

### Update Package List

```
sudo apt-get update
```

This **refreshes the package database** from repositories.

### Upgrade Installed Packages

```
sudo apt-get upgrade
```

This installs **latest versions of installed software**.

### One-liner Command

```
sudo apt-get update && sudo apt-get upgrade -y
```

Explanation:

- `update` → refresh package list
    
- `upgrade` → install updates
    
- `-y` → automatically confirm installation
    

---

# Installing Software

To install a package from the repository:

```
sudo apt-get install nmap -y
```

Example installs the **nmap network scanning tool**.

---

# Viewing Installed Packages

To see all installed packages:

```
apt list --installed
```

---

# Removing Software Packages

Linux provides two methods to uninstall software.

### Remove (Partial Removal)

```
sudo apt-get remove nmap
```

- Removes the program
    
- Keeps configuration files
    

Useful if you plan to **reinstall later**.

---

### Purge (Complete Removal)

```
sudo apt-get purge nmap
```

- Removes program
    
- Removes configuration files
    

Used for **complete cleanup**.

---

# dpkg (Debian Package Manager)

`dpkg` is a **low-level package manager** used to handle `.deb` files directly.

Unlike APT, it **does not automatically resolve dependencies**.

### Install a .deb Package

```
sudo dpkg -i package-name.deb
```

### Remove a Package

```
sudo dpkg -r package-name
```

### Complete Removal

```
sudo dpkg --purge package-name
```

Example:

```
sudo apt install ./discord-0.0.80.deb
```

APT can also install `.deb` files and resolve dependencies automatically.

---

# pip (Python Package Manager)

`pip` is used to **install and manage Python libraries** from the **Python Package Index (PyPI)**.

### Install a Python Package

```
pip install package-name
```

### Remove a Package

```
pip uninstall package-name
```

### List Installed Packages

```
pip list
```

Example:

```
pip install requests
```

---

# Adding Repositories

Repositories are defined in the file:

```
/etc/apt/sources.list
```

To edit the file:

```
nano /etc/apt/sources.list
```

You can add new repositories if software is **not available in default repositories**.

Example repository entry:

```
deb [arch=amd64] http://packages.microsoft.com/repos/vscode stable main
```

After adding repository:

```
sudo apt update 
sudo apt install code
```

This installs **Visual Studio Code**.

---

# Repository Categories

Some Linux distributions organize repositories into categories.

|Category|Description|
|---|---|
|main|Official supported open-source software|
|universe|Community maintained software|
|multiverse|Software with copyright restrictions|
|restricted|Proprietary drivers|
|backports|Software from newer releases|

Avoid using **testing or unstable repositories** because they may break the system.

---

# Installing Software with Git

Sometimes software is **not available in repositories** but available on **GitHub**.

GitHub hosts **open-source projects and tools**.

### Clone Repository

```
git clone https://github.com/vanhauser-thc/thc-hydra
```

This downloads the project to your system.

---

# Compiling Software from Source

After cloning, go to the project directory:

```
cd thc-hydra
```

### Configure

```
./configure
```

Checks system dependencies.

### Compile Source Code

```
make
```

Builds the executable program.

### Install Program

```
make install
```

Copies the compiled files to system directories.

---

# Summary of Software Management Tools

|Tool|Purpose|
|---|---|
|apt / apt-get|Install and manage packages|
|apt-cache|Search packages|
|dpkg|Manage `.deb` files|
|pip|Install Python libraries|
|git|Download projects from GitHub|
|make|Compile source code|

---

If you want, I can also make a **very short 1-page revision sheet for Linux commands (network + software management)** which is **perfect for exams or quick memorization**.