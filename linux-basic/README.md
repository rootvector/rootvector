# Linux Basics for Hackers

*By OccupyTheWeb*

------------------------------------------------------------------------

## Brief Contents

1.  [Getting Started with the Basics](#1-getting-started-with-the-basics)
2.  [Text Manipulation](#2-text-manipulation)
3.  Analyzing and Managing Networks
4.  Adding and Removing Software
5.  Controlling File and Directory Permissions
6.  Process Management
7.  Managing User Environment Variables
8.  Bash Scripting
9.  Compressing and Archiving
10. Filesystem and Storage Device Management
11. The Logging System
12. Using and Abusing Services
13. Becoming Secure and Anonymous
14. Understanding and Inspecting Wireless Networks
15. Managing the Linux Kernel and Loadable Kernel Modules
16. Automating Tasks with Job Scheduling
17. Python Scripting Basics for Hackers

------------------------------------------------------------------------

## 1. Getting Started with the Basics

### Finding Yourself with `pwd`

``` bash
pwd
```

**Purpose:** Shows the current working directory.

------------------------------------------------------------------------

### Checking Your Login with `whoami`

``` bash
whoami
```

**Purpose:** Displays the current logged-in user.

------------------------------------------------------------------------

### Navigating the Linux Filesystem

``` bash
cd /etc
cd ..
cd ../..
```

-   `..` → Move up one directory
-   `../..` → Move up two directories

------------------------------------------------------------------------

### Listing Directory Contents with `ls`

``` bash
ls
ls -l
ls -la
```

-   `-l` → Long listing format\
-   `-a` → Show hidden files

------------------------------------------------------------------------

### Getting Help

``` bash
aircrack-ng --help
nmap -h
```

-   `--` is used for full-word options\
-   `-` is used for single-letter options

------------------------------------------------------------------------

### Using Manual Pages

``` bash
man aircrack-ng
```

------------------------------------------------------------------------

## Finding Files

### Using `locate`

``` bash
locate aircrack-ng
```

> Note: `locate` uses a database that may not update instantly.

------------------------------------------------------------------------

### Using `whereis`

``` bash
whereis aircrack-ng
```

------------------------------------------------------------------------

### Using `which`

``` bash
which aircrack-ng
```

------------------------------------------------------------------------

### Using `find`

**Syntax:**

``` bash
find directory options expression
```

**Example:**

``` bash
find / -type f -name apache2
```

------------------------------------------------------------------------

### Filtering with `grep`

``` bash
ps aux | grep apache2
```

------------------------------------------------------------------------

## Modifying Files and Directories

### Create or Overwrite a File

``` bash
cat > hackingskills
```

### Append to a File

``` bash
cat >> hackingskills
```

### Create a File

``` bash
touch newfile
```

### Create a Directory

``` bash
mkdir newdirectory
```

### Copy a File

``` bash
cp oldfile /root/mydir
```

### Rename or Move a File

``` bash
mv source destination
```

### Remove a File

``` bash
rm filename
```

### Remove a Directory

``` bash
rmdir directoryname
rm -r newdirectory
```

------------------------------------------------------------------------

## 2. Text Manipulation

(Add your notes here as you continue learning.)

------------------------------------------------------------------------

## Mission

This repository documents my ethical hacking journey through structured
notes, commands, and lab observations.

Consistency \> Motivation.
