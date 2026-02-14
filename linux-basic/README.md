# Linux Basics For Hackers
- *By OccupyTheWeb

## BRIEF CONTENTS

---
**
1. [Geting Started with the Basics](#geting-started-with-the-basics)
2. [Text Manipulation](#text-manipulation)
3. Analyzing and Managing Network
4. Adding and Removing Software
5. Controlling File and Directory Permissions
6. Process Management
7. Managing User Environment Variables
8. Bash Scripting
9. Compressing and Archiving 
10. Filesystem and Storage Device Management
11. The Logging System
12. Using and Abusing Services
13. Becoming Secure and Anonymous
14. Understanding and Inspecting Wireless Networks
15. Managing the Linux Kernel and Loadable Kernel Modules
16. Automating Tasks with Job Scheduling
17. Python Scripting Basics for Hackers **

---

## 1. Geting Started with the Basics

### Basic Commands in Linux

###*Finding Yourself with pwd*

```bash
pwd
```

###*Checking Your Login with whoami*
```bash
whoami
```

### Navigating the Linux Filesystem

###*Navigating the Linux Filesystem*
```bash
cd /etc

cd ..

cd ../..
```

- You would use .. to move up one level.
- You would use ../.. to move up two levels.
- You would use ../../.. to move up three levels, and so on.

###*Listing the Contents of a Directory with ls*
```bash
ls

ls -l       # FOR LONG LIST OF FILES AND FOLDERS

ls -la      # LONG LISTING AND HIDDEN FILE AND FOLDER LISTING

```

###*Getting Help*
```bash
aricrack-ng --help

nmap -h
```

*Note the double dash here. The convention in Linux is to use a double
dash (--) before word options, such as help, and a single dash (-) before
single-letter options, such as –h.*

###*Referencing Manual Pages with man*
```bash
man aircrack-ng
```

### Finding Stuff

###*Searching with locate*
```bash
locate aircrack-ng
```

*locate
uses a database that is usually only updated once a day, so if you just created
a file a few minutes or a few hours ago, it might not appear in this list until
the next day. It’s worth knowing the disadvantages of these basic commands
so you can better decide when best to use each one.*

###*Finding Binaries with whereis*
```bash
whereis aircrack-ng
```
###*Finding Binaries in the PATH Variable with which*

The which command is even more specific: it only returns the location of
the binaries in the PATH variable in Linux.

```bash
which aircrack-ng
```
###*Performing More Powerful Searches with find*

*syntax*

`find directory options expression`

*example*
```bash
find / -type f -name apache2
```

> A Quic Look At WildCards

Let’s say we’re doing a search on a directory that has the files cat, hat, what,
and bat. The ? wildcard is used to represent a single character, so a search
for ?at would find hat, cat, and bat but not what, because at in this filename is
preceded by two letters. The [] wildcard is used to match the characters that
appear inside the square brackets. For example, a search for [c,b]at would
match cat and bat but not hat or what. Among the most widely used wildcards
is the asterisk (*), which matches any character(s) of any length, from none to
an unlimited number of characters. A search for *at, for example, would find
cat, hat, what, and bat.

###*Filtering with grep*

```bash
ps aux | grep apache2
```

### Modifying Files and Directories

###*Creating Files*

###*Concatenation with cat*
```bash
cat > hackingskills     # Create new file or change existing data or overwrite data of file using > operator

cat >> hackingskills  # >> sing use for append text in file
```

###*File Creation with touch*
```bash
touch newfile
```

###*Creating a Directory*
```bash
mkdir newdirectory
```

###*Copying a File*
```bash
cp oldfile /root/mydir      # oldfile is a source and new file is a destination.
```

###*Renaming a File*

*syntax*
```bash
mv source destination
```

###*Removing a File*
```bash
rm filename
```

###*Removing a Directory*
```bash
rmdir directoryname     # if directory was empty

rm -r newdirectory      # if directory contain a files in it. -r switch are used.
```

---

## 2. Text Manipulation



