# sysopctl
```
yashikjain@LAPTOP-UV7S5VGB:~/sysopctl$ ./sysopctl.sh --help
Usage: sysopctl <command> [options]
Commands:
  service list   - List all running processes (replaces system services in WSL)
  service start  - Start a specified service
  service stop   - Stop a specified service
  system load    - View current system load
  disk usage     - Show disk usage statistics
  process monitor - Monitor system processes (like top/htop)
  logs analyze    - Analyze system logs for critical entries
  backup <path>   - Backup system files from the specified path
  version         - Show version information
  ```

```
yashikjain@LAPTOP-UV7S5VGB:~/sysopctl$ ./sysopctl.sh --version
sysopctl version v0.1.0
```
```
List Running Services:
yashikjain@LAPTOP-UV7S5VGB:~/sysopctl$ ./sysopctl.sh service list
Listing all running processes...
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.7  0.0   2236  1564 ?        Sl   19:20   0:06 /init
root         7  0.0  0.0   1824    88 ?        Ss   19:20   0:00 /init
root         8  0.0  0.0   1824   104 ?        S    19:20   0:00 /init
yashikj+     9  0.0  0.0   6204  5220 pts/0    Ss   19:20   0:00 -bash
root        74  0.0  0.0   2572   548 ?        Ss   19:23   0:00 /init
root        75  0.0  0.0   2572   548 ?        S    19:23   0:00 /init
yashikj+    76  0.0  0.0   2888   948 pts/1    Ss+  19:23   0:00 /bin/sh -c cd '/home/yashikjain/sysopctl' && /bin/sh
yashikj+    77  0.0  0.0   2888  1892 pts/1    S+   19:23   0:00 /bin/sh
yashikj+   710  0.0  0.6 991972 49796 pts/1    Sl+  19:24   0:00 /home/yashikjain/.vscode-remote-containers/bin/fabdb6a3
yashikj+   735  0.0  0.0   2888   976 pts/1    S+   19:24   0:00 /bin/sh
yashikj+  3255  0.0  0.0   4780  3312 pts/0    S+   19:34   0:00 /bin/bash ./sysopctl.sh service list
yashikj+  3256  0.0  0.0   7480  3196 pts/0    R+   19:34   0:00 ps aux
```

```
View System Load:
yashikjain@LAPTOP-UV7S5VGB:~/sysopctl$ ./sysopctl.sh system load
Current system load averages:
 19:35:07 up 14 min,  0 users,  load average: 0.02, 0.01, 0.00
 ```

 ```
 Part 2 | Level Intermediate 

• Manage System Services:

Start a service: $ sysopctl service start <service-name>
yashikjain@LAPTOP-UV7S5VGB:~/sysopctl$ ./sysopctl.sh service start apache2
Starting service: apache2
Service 'apache2' started successfully (simulated).


Stop a service: $ sysopctl service stop <service-name>
yashikjain@LAPTOP-UV7S5VGB:~/sysopctl$ ./sysopctl.sh service stop apache2
Stopping service: apache2
Service 'apache2' stopped successfully (simulated).
```

```
Check Disk Usage:
yashikjain@LAPTOP-UV7S5VGB:~/sysopctl$ ./sysopctl.sh disk usage
Disk usage statistics by partition:
Filesystem      Size  Used Avail Use% Mounted on
/dev/sdc        251G  1.5G  237G   1% /
none            3.9G   28K  3.9G   1% /mnt/wslg
none            3.9G  4.0K  3.9G   1% /mnt/wsl
tools           476G  366G  110G  77% /init
none            3.9G     0  3.9G   0% /run
none            3.9G     0  3.9G   0% /run/lock
none            3.9G     0  3.9G   0% /run/shm
none            3.9G     0  3.9G   0% /run/user
tmpfs           3.9G     0  3.9G   0% /sys/fs/cgroup
drivers         476G  366G  110G  77% /usr/lib/wsl/drivers
lib             476G  366G  110G  77% /usr/lib/wsl/lib
none            3.9G   76K  3.9G   1% /mnt/wslg/versions.txt
none            3.9G   76K  3.9G   1% /mnt/wslg/doc
drvfs           476G  366G  110G  77% /mnt/c
```

```
• Monitor System Processes:

yashikjain@LAPTOP-UV7S5VGB:~/sysopctl$ ./sysopctl.sh process monitor
Monitoring system processes...
top - 19:39:10 up 19 min,  0 users,  load average: 0.00, 0.00, 0.00
Tasks:  12 total,   1 running,  11 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   7831.0 total,   7378.5 free,    263.8 used,    188.7 buff/cache
MiB Swap:   2048.0 total,   2048.0 free,      0.0 used.   7344.9 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
    1 root      20   0    2412   1188   1108 S   0.0   0.0   0:08.18 init
    7 root      20   0    1824     88      0 S   0.0   0.0   0:00.00 init
    8 root      20   0    1824    104      0 S   0.0   0.0   0:00.02 init
    9 yashikj+  20   0    6204   5220   3460 S   0.0   0.1   0:00.06 bash
   74 root      20   0    2572    548      0 S   0.0   0.0   0:00.00 init
   75 root      20   0    2572    548      0 S   0.0   0.0   0:00.31 init
   76 yashikj+  20   0    2888    948    848 S   0.0   0.0   0:00.00 sh
   77 yashikj+  20   0    2888   1892   1768 S   0.0   0.0   0:00.00 sh
  710 yashikj+  20   0  991972  49796  41276 S   0.0   0.6   0:00.28 node
  735 yashikj+  20   0    2888    976    876 S   0.0   0.0   0:00.00 sh
 5491 yashikj+  20   0    4780   3388   3144 S   0.0   0.0   0:00.00 sysopctl.sh
 5492 yashikj+  20   0    7792   3232   2868 R   0.0   0.0   0:00.00 top
 ```

 ```
 Analyze System Logs:
 yashikjain@LAPTOP-UV7S5VGB:~/sysopctl$ ./sysopctl.sh logs analyze
Analyzing system logs for recent critical entries...
No journal files were found.
-- No entries --
```

```
 Backup System Files:

 yashikjain@LAPTOP-UV7S5VGB :~ /sysopctl$ . /sysopctl. sh backup /home/user/Document
 Backing up files from /home/user/Documents ...
sending incremental file list
rsync: [sender] change_dir "/home/user" failed: No such file or directory (2)
sent 19 bytes received 12 bytes 62.00 bytes/sec
total size is 0 speedup is 0.00
rsync error: some files/attrs were not transferred (see previousferrors) (code 23) at main.c(1338) [sender=3.2.7]
Backup completed successfully.

```


# **sysopctl Command Documentation**

## **Overview**

**sysopctl** is a custom command-line tool designed to enhance system administration capabilities on Linux-based systems. It allows users to manage system resources effectively, perform system health checks, and automate various tasks like process monitoring, log analysis, and file backups. The tool aims to simplify administrative tasks with intuitive commands and features.

---

## **Command Features and Usage**

### **1. Basic Features**

#### **Manual Page**
A detailed manual page for `sysopctl` is available. Users can access it with the command:
```bash
man sysopctl
```
This manual provides in-depth information on command usage, options, and examples.

#### **Help Option**
To display a quick usage guide, use:
```bash
sysopctl --help
```
**Output:**
```
Usage: sysopctl <command> [options]
Commands:
  service list       - List all running processes (replaces system services in WSL)
  service start      - Start a specified service
  service stop       - Stop a specified service
  system load        - View current system load
  disk usage         - Show disk usage statistics
  process monitor    - Monitor system processes (like top/htop)
  logs analyze       - Analyze system logs for critical entries
  backup <path>      - Backup system files from the specified path
  version            - Show version information
```

#### **Version Information**
To check the current version of the tool:
```bash
sysopctl --version
```
**Output:**
```
sysopctl version v0.1.0
```

---

### **2. System Management Operations**

#### **Part 1: Easy Level Features**

##### **List Running Services**
Command:
```bash
sysopctl service list
```
**Description:** Lists all running processes as an alternative to managing system services on WSL.

**Example Output:**
```
Listing all running processes...
USER       PID  %CPU %MEM COMMAND
root         1   0.2  0.1 /sbin/init
user      2345   5.0  1.2 /usr/bin/python3 my_script.py
```

##### **View System Load**
Command:
```bash
sysopctl system load
```
**Description:** Displays the current system load averages using the `uptime` command.

**Example Output:**
```
Current system load averages:
 15:25:03 up  3:45,  2 users,  load average: 0.25, 0.30, 0.20
```

---

#### **Part 2: Intermediate Level Features**

##### **Manage System Services**
- **Start a Service**
  ```bash
  sysopctl service start <service-name>
  ```
  **Description:** Simulates starting a specified service (relevant for non-WSL environments).

  **Example Output:**
  ```
  Starting service: apache2
  Service 'apache2' started successfully (simulated).
  ```

- **Stop a Service**
  ```bash
  sysopctl service stop <service-name>
  ```
  **Description:** Simulates stopping a specified service.

  **Example Output:**
  ```
  Stopping service: apache2
  Service 'apache2' stopped successfully (simulated).
  ```

##### **Check Disk Usage**
Command:
```bash
sysopctl disk usage
```
**Description:** Displays disk usage statistics for all mounted partitions using the `df -h` command.

**Example Output:**
```
Disk usage statistics by partition:
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1       50G   25G   25G  50% /
```

---

#### **Part 3: Advanced Level Features**

##### **Monitor System Processes**
Command:
```bash
sysopctl process monitor
```
**Description:** Monitors system processes in real-time, similar to `top` or `htop`.

**Example Output:**
```
Monitoring system processes...
PID  USER    PR  NI  VIRT    RES    SHR S %CPU %MEM TIME+  COMMAND
1234 root    20   0 123456  65432  5678 S  12.3  3.1 0:45.67 my_process
```

##### **Analyze System Logs**
Command:
```bash
sysopctl logs analyze
```
**Description:** Analyzes system logs for recent critical entries using the `journalctl` command.

**Example Output:**
```
Analyzing system logs for recent critical entries...
-- Logs begin at 2024-01-01 --
CRIT: System failure detected at 12:45 PM
CRIT: Disk error at sector 54321
```

##### **Backup System Files**
Command:
```bash
sysopctl backup <path>
```
**Description:** Backups files from the specified path using `rsync`.

**Example Output:**
```
Backing up files from /home/user/documents...
Files successfully backed up to /home/user/backup.
```

---

## **System Workflow and Architecture**

### **1. Workflow**
1. **User Input:** Command and options are entered by the user.
2. **Argument Parsing:** The script validates and processes the input arguments.
3. **Command Execution:** The appropriate functionality is triggered based on the input.
4. **Output:** Results are displayed to the user in a human-readable format.

### **2. System Architecture**
The `sysopctl` tool relies on native Linux utilities like `ps`, `df`, `uptime`, `top`, `journalctl`, and `rsync`. The script acts as a wrapper, integrating these utilities to provide a seamless and cohesive interface.

---

## **Version Control**
- All code and documentation are stored in a  Git repository to ensure version tracking and secure collaboration.
- Repository structure:
  ```
  sysopctl/
  ├── sysopctl.sh       # Main script
  ├── README.md        # Documentation
  
  ```

---



---

## **Confidentiality**
This documentation and code are strictly confidential and must not be shared with anyone outside the project team. Unauthorized distribution is prohibited.

---

