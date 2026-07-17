# Day 6 - Linux Fundamentals Part 2

## What is a command flag?

* A flag (or switch) is an extra option added to a command to change or extend how it behaves.
* It usually starts with a single or double dash, such as `-l` or `--help`.

## What does --help do?

* It acts as a quick, built-in cheat sheet for a command right inside the terminal.
* It instantly lists what the command does along with its most common flags.

## What does man do?

* It stands for "manual" and opens the official, highly detailed user guide for a specific command.
* Unlike `--help`, it provides a complete breakdown of every single feature and configuration option available.

## File and folder commands

### touch

* Creates a brand-new, empty file in your current folder.

### mkdir

* Stands for "make directory"—it creates a new, empty folder.

### cp

* Copies a file or folder from one location to another, leaving the original file exactly where it was.

### mv

* Moves a file or folder to a completely new location, or renames a file if kept in the same spot.

### rm

* Removes (deletes) a file or folder permanently from the system.

### file

* Inspects a file and tells you exactly what type of data it contains (like plain text, a folder, or an executable script).

## Linux file permissions

### Read permission

* Represented by the letter `r` (or the number 4), it allows a user to open and read the contents of a file or folder.

### Write permission

* Represented by the letter `w` (or the number 2), it allows a user to modify, edit, or completely delete a file or folder.

### Execute permission

* Represented by the letter `x` (or the number 1), it allows a user to run a file as a program/script, or enter a folder using `cd`.

### Owner, group, and others

* **Owner** is the single user account that created the file.
* **Group** is a collection of specific users who all share the same access settings.
* **Others** represents every regular user on the local system who isn't the owner or in the group.

## Important Linux directories

### /etc

* Stores system-wide configuration settings and critical files like `passwd` and `shadow`.

### /var

* Stores dynamic "variable" data that shifts constantly, most importantly system log files under `/var/log`.

### /root

* The private home directory reserved completely for the administrative "root" superuser.

### /tmp

* A temporary folder where any user can write tools or scripts, which gets wiped clean when the system reboots.

### /home

* The main directory where regular system users keep their personal folders, files, and configurations.

## cp vs mv

* `cp` duplicates an item, creating a brand-new match while keeping the original file untouched.
* `mv` physically shifts the original item to a new location, leaving absolutely nothing behind in the old directory.

## Three things I found difficult

1. Figuring out the exact math when converting symbolic permission groups (like `rwxr-xr-x`) into three-digit numbers.
2. Understanding why the terminal says "Permission Denied" on a file even if my user account created it.
3. Keeping track of the exact command syntax rules when moving directories versus single text files.

## Interview questions

### What does rwx mean?

> "It stands for Read, Write, and Execute, which are the three core permission types assigned to Owners, Groups, and Others to control file access in Linux."

### How do you check file permissions?

> "You run the `ls -l` command, which displays a detailed list of your files along with their explicit permission symbols in the very first column."

### What is the difference between cp and mv?

> "The `cp` command creates a duplicate copy of a file in a new location without modifying the original, while `mv` physically repositions or renames the file, deleting it from its old location."

### What is stored inside /var?

> "It holds variable data that changes constantly while the system is running, including web server files, databases, and crucial system security logs."

### What does the man command do?

> "It displays the built-in reference manual for a command, giving a security analyst a full technical breakdown of what that specific tool does and how its switches work."

## Practice completed

* Completed the Linux Fundamentals Part 2 room on TryHackMe.
* Successfully tested user restrictions using `su` and `sudo` in the live lab terminal.
* Created, modified, and managed text files across multiple standard file paths.
