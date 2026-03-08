
Linux uses a **permission-based security model** to control who can access files and directories.

The system mainly uses:

- **Users**
    
- **Groups**
    
- **Permissions**
    

This structure helps **protect system resources and maintain security**.

---

# Root User vs Regular Users

### Root User (Superuser)

The **root user** has **complete control over the system**.

Capabilities:

- Modify any file
    
- Install/remove software
    
- Change system settings
    
- Manage users and groups
    

Because of this power, misuse of root privileges can create **security risks**.

---

### Regular Users

Regular users have **limited permissions**.

They can:

- Access their own files
    
- Run programs
    
- Use system resources
    

They **cannot modify system files** without root privileges.

---

# Adding a User

To create a new user in Linux:

```bash
sudo adduser john
```

During creation the system will:

1. Create a user account
    
2. Assign a **User ID (UID)**
    
3. Create a **home directory**
    

Example:

```
/home/john
```

---

# Verify User Creation

User information is stored in:

```
/etc/passwd
```

Check if the user exists:

```bash
grep john /etc/passwd
```

Example output:

```
john:x:1002:1002:john:/home/john:/bin/bash
```

This shows:

- username
    
- UID
    
- GID
    
- home directory
    
- default shell
    

---

# Groups in Linux

A **group** is a collection of users with similar access needs.

Groups simplify permission management.

Example groups:

- Developers
    
- Network Administrators
    
- Database Administrators
    

Instead of assigning permissions to **each user**, administrators assign permissions to **groups**.

---

# Creating a Group

```bash
sudo groupadd developers
```

Verify group:

```bash
cat /etc/group | grep developers
```

Group information is stored in:

```
/etc/group
```

---

# Types of Groups

## 1. Primary Group

Each user has **one primary group**.

Characteristics:

- Created when user account is created
    
- Usually same name as the user
    
- Determines default group ownership of files
    

Example:

User: `john`  
Primary group: `john`

Stored in:

```
/etc/passwd
```

---

## 2. Secondary Groups

Users can belong to **multiple secondary groups**.

Used to give **extra permissions**.

Example groups:

- developers
    
- admins
    
- finance
    

Stored in:

```
/etc/group
```

---

# Add User to Group

Example: add **john** to **developers group**

```bash
sudo usermod -aG developers john
```

Verify:

```bash
cat /etc/group | grep developers
```

Output:

```
developers:x:1003:john
```

---

# Linux File Permissions

Each file or directory has **three types of permissions**.

|Permission|Meaning|
|---|---|
|r|Read|
|w|Write|
|x|Execute|

---

# Permission Categories

Permissions are assigned to **three user categories**.

|Category|Meaning|
|---|---|
|Owner (u)|User who owns the file|
|Group (g)|Group associated with file|
|Others (o)|All other users|

---

# Viewing Permissions

Use:

```bash
ls -l
```

Example:

```
drwxrwxr-x 2 kali kali test
-rw-rw-r-- 1 kali kali test.txt
```

---

# Understanding Permission Output

Example:

```
drwxrwxr-x
```

Breakdown:

|Part|Meaning|
|---|---|
|d|Directory|
|rwx|Owner permissions|
|rwx|Group permissions|
|r-x|Others permissions|

---

Example file:

```
-rw-rw-r--
```

Meaning:

|User|Permissions|
|---|---|
|Owner|read + write|
|Group|read + write|
|Others|read only|

---

# Changing Permissions with chmod

Permissions can be changed using:

```bash
chmod
```

Two methods:

1. **Numeric (Octal) notation**
    
2. **Symbolic (UGO) notation**
    

---

# Numeric Permission Method

Permission values:

|Permission|Value|
|---|---|
|Read|4|
|Write|2|
|Execute|1|

Add them to create permissions.

Example:

|Permission|Value|
|---|---|
|rwx|7|
|rw-|6|
|r-x|5|
|r--|4|

---

Example:

```
chmod 755 test.txt
```

Meaning:

|User|Permission|
|---|---|
|Owner|rwx (7)|
|Group|r-x (5)|
|Others|r-x (5)|

Result:

```
-rwxr-xr-x
```

---

Example:

```
chmod 651 test.txt
```

Meaning:

|User|Permission|
|---|---|
|Owner|rw-|
|Group|r-x|
|Others|--x|

Result:

```
-rw-r-x--x
```

---

# Symbolic Permission Method (UGO)

UGO stands for:

|Symbol|Meaning|
|---|---|
|u|user (owner)|
|g|group|
|o|others|

Operators:

|Operator|Meaning|
|---|---|
|+|add permission|
|-|remove permission|
|=|set exact permission|

---

Examples:

Add execute permission to owner:

```bash
chmod u+x test.txt
```

Remove write permission from group:

```bash
chmod g-w test.txt
```

Set read-only permission for others:

```bash
chmod o=r test.txt
```

Remove all group permissions:

```bash
chmod g= test.txt
```

---

# Changing File Ownership

Ownership can be changed using **chown**.

Example:

```bash
sudo chown john test.txt
```

Now **john becomes the file owner**.

---

# Changing Group Ownership

Change group using **chgrp**.

Example:

```bash
sudo chgrp developers test.txt
```

Now file group becomes:

```
developers
```

---

# Default Permissions with umask

**umask** controls default permissions for newly created files.

Formula:

|Type|Base Permission|
|---|---|
|File|666|
|Directory|777|

Example:

```
umask 022
```

Results:

|Object|Final Permission|
|---|---|
|File|644|
|Directory|755|

---

Example:

```
umask 027
```

Results:

|Object|Permission|
|---|---|
|File|640|
|Directory|750|

---

# Special Permissions

Linux has **three special permissions**:

|Permission|Name|
|---|---|
|4|SUID|
|2|SGID|
|1|Sticky Bit|

---

# SUID (Set User ID)

When SUID is set:

A user running the program **inherits the file owner's permissions**.

Example:

```bash
chmod 4644 file
```

Output:

```
-rwSr--r--
```

Common example:

Password changing program accessing:

```
/etc/shadow
```

---

# SGID (Set Group ID)

When SGID is set:

- Program runs with **group permissions**
    
- Files created in a directory **inherit the directory’s group**
    

Example:

```bash
chmod 2644 test2
```

Result:

```
-rw-r-Sr--
```

---

# Sticky Bit

Sticky bit prevents **users from deleting other users' files** in shared directories.

Example:

```
/tmp
```

Set sticky bit:

```bash
chmod +t directory
```

Example output:

```
drwxrwxrwt
```

Rules:

Only these can delete files:

- file owner
    
- directory owner
    
- root
    

---

# Finding SUID Files (Privilege Escalation)

Attackers and penetration testers search for **SUID files owned by root**.

Command:

```bash
find / -user root -perm -4000 2>/dev/null
```

Explanation:

|Part|Meaning|
|---|---|
|find /|search entire system|
|-user root|files owned by root|
|-perm -4000|files with SUID|
|2>/dev/null|hide errors|

These files can sometimes be used for **privilege escalation attacks**.

---

# Important Commands Summary

|Command|Purpose|
|---|---|
|adduser|create user|
|groupadd|create group|
|usermod|modify user groups|
|chmod|change permissions|
|chown|change owner|
|chgrp|change group|
|umask|set default permissions|
|find|search files|

---

If you want, I can also give you a **very short Linux permissions cheat sheet (15 most important commands hackers use)** that helps a lot in **CTF, Kali Linux labs, and pentesting exams**.