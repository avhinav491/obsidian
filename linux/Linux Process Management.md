

In Linux, a **process** is a **running instance of a program**.

A process includes:

- Program code
    
- Current activity
    
- System resources (CPU, memory, files)
    

Each process is identified by a **Process ID (PID)**.

Processes can communicate using:

- Pipes
    
- Signals
    
- Shared memory
    

---

# Process Creation in Linux

Linux creates processes using **fork()**.

### Fork Process

- The **parent process duplicates itself**
    
- A **child process** is created
    

After that, the child may run another program using **exec()**.

Flow:

```
Parent Process
      │
     fork()
      │
Child Process
      │
     exec()
      │
New Program Runs
```

---

# Process States in Linux

A process can be in different states.

|State|Meaning|
|---|---|
|Running|Currently using CPU|
|Sleeping|Waiting for resource|
|Stopped|Paused process|
|Zombie|Process finished but not cleaned|

---

# Root Process (Init/Systemd)

All processes originate from the **first process**.

Traditionally:

```
init (PID 1)
```

Modern systems use:

systemd

Responsibilities:

- Start system services
    
- Manage system startup
    
- Manage orphan processes
    
- Handle shutdown
    

---

# Viewing Processes

## Basic Process View

Command:

```bash
ps
```

Example output:

```
PID TTY      TIME CMD
1377 pts/0   00:00:00 bash
1488 pts/0   00:00:00 ps
```

Columns:

|Column|Meaning|
|---|---|
|PID|Process ID|
|TTY|Terminal|
|TIME|CPU time used|
|CMD|Command name|

---

# Viewing All Processes

Command:

```bash
ps aux
```

This shows **all running processes in the system**.

Important columns:

|Column|Meaning|
|---|---|
|USER|Process owner|
|PID|Process ID|
|%CPU|CPU usage|
|%MEM|Memory usage|
|COMMAND|Running program|

---

# Filtering Processes

Sometimes you only want **specific processes**.

Use **grep** with ps.

Example:

```bash
ps aux | grep apache2
```

Example output:

```
root      7800  apache2
www-data  7802  apache2
www-data  7803  apache2
```

This shows processes related to:

Apache HTTP Server

---

# Monitoring Processes in Real Time

Use:

```bash
top
```

The **top command** shows real-time process information.

Information displayed:

|Field|Meaning|
|---|---|
|%CPU|CPU usage|
|%MEM|Memory usage|
|TIME+|CPU time|
|COMMAND|Program name|

Other system info:

- CPU usage
    
- Memory usage
    
- Load average
    
- Running tasks
    

Exit:

```
q
```

---

# Services and Daemons

Background services are called **daemons**.

Daemon programs usually end with **d**.

Examples:

|Service|Daemon|
|---|---|
|SSH|sshd|
|System manager|systemd|
|Web server|httpd / apache2|

---

# Types of Services

## 1. Internal Services

System startup services.

Examples:

- Hardware drivers
    
- Logging services
    
- Network services
    

---

## 2. User-Installed Services

Installed by the user.

Examples:

|Service|Purpose|
|---|---|
|Apache|Web server|
|MySQL|Database|
|SSH|Remote login|

---

# Managing Services with systemctl

Start a service:

```bash
systemctl start apache2
```

Check status:

```bash
systemctl status apache2
```

Stop service:

```bash
systemctl stop apache2
```

Restart service:

```bash
systemctl restart apache2
```

---

# Killing Processes

Sometimes processes:

- freeze
    
- consume high CPU
    
- behave abnormally
    

You can terminate them using:

```bash
kill <PID>
```

Example:

```bash
kill 13831
```

---

# Viewing Signals

Linux has **64 signals**.

View them:

```bash
kill -l
```

---

# Common Linux Signals

|Signal|Number|Purpose|
|---|---|---|
|SIGHUP|1|Reload configuration|
|SIGINT|2|Ctrl+C interrupt|
|SIGQUIT|3|Quit program|
|SIGKILL|9|Force kill|
|SIGTERM|15|Graceful termination|
|SIGSTOP|19|Pause process|
|SIGTSTP|20|Ctrl+Z suspend|

---

# Force Kill a Process

Example:

```bash
kill -9 44000
```

Signal used:

```
SIGKILL
```

This **immediately terminates the process**.

---

# Killing Processes by Name

Instead of PID you can use:

### pkill

```bash
pkill nano
```

### killall

```bash
killall nano
```

---

# Running Processes in Background

To run a command in the background:

```bash
sleep 100 &
```

Example output:

```
[1] 24213
```

---

# Suspend a Process

Press:

```
CTRL + Z
```

This pauses the process.

---

# Move Process to Background

Use:

```bash
bg
```

---

# List Background Jobs

```bash
jobs
```

Example:

```
[2]+ Running sleep 400
```

---

# Bring Process to Foreground

Use:

```bash
fg %2
```

Now the process runs in the **foreground again**.

---

# Important Process Management Commands

|Command|Purpose|
|---|---|
|ps|view processes|
|ps aux|view all processes|
|top|real-time monitoring|
|kill|terminate process|
|pkill|kill by name|
|killall|kill all instances|
|jobs|show background jobs|
|bg|move process to background|
|fg|bring process to foreground|
|systemctl|manage services|

---

✅ **Simple Memory Trick**

```
ps      → process snapshot
top     → real-time processes
kill    → terminate process
jobs    → background jobs
fg/bg   → foreground/background
systemctl → manage services
```

---

If you want, I can also give you a **super short “Linux Process Management Cheat Sheet for Hackers (15 commands only)”** that is **very useful in Kali Linux, CTFs, and penetration testing exams**.