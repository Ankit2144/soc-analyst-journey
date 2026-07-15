# Day 5 - Linux Fundamentals Part 1

## What is Linux?

* Linux is a free, open-source operating system, just like Windows or macOS.
* Instead of relying on a desktop interface, it is primarily managed using a text-based terminal.

## Where do companies use Linux?

* Companies use Linux to run internet servers, cloud setups (like AWS and Azure), and databases.
* It forms the backend backbone of almost all modern corporate IT networks.

## Why do SOC analysts need Linux?

* Most security tools and web servers run on Linux systems.
* Analysts must know how to navigate the Linux terminal to track down, read, and analyze security logs during an alert.

## Commands

### echo

* Prints text or variables directly to the terminal screen.

### whoami

* Displays the exact username of the account you are currently logged into.

### ls

* Lists all the files and folders inside your current directory.

### cd

* Changes your current directory, allowing you to move into a different folder.

### pwd

* Prints the working directory, showing the exact folder path you are currently standing in.

### cat

* Reads and displays the entire text content of a file on the terminal screen.

### find

* Searches the system to locate files and folders based on names, dates, or sizes.

### grep

* Searches through files to find and extract lines that contain a specific keyword.

## Operators

### Greater-than operator: >

* Redirects command output to a file, completely overwriting any old data inside it.

### Double greater-than operator: >>

* Redirects command output to a file, appending the new text to the end without erasing what was already there.

### AND operator: &&

* Chains two commands together, running the second command only if the first one finishes successfully.

## Practice completed

* Finished the Linux Fundamentals Part 1 room on TryHackMe.
* Practiced navigating the filesystem and manipulating text files using the terminal.

## Three things I found difficult

1. Remembering the exact syntax and flags needed to make the `find` command work correctly.
2. Keeping track of absolute versus relative file paths when jumping between deeply nested folders.
3. Visualizing how data flows when combining multiple commands and operators together for the first time.

## Interview questions

### What is Linux, and why do SOC teams use it?

> "Linux is an open-source operating system that powers the vast majority of enterprise servers and cloud environments. SOC teams use it constantly because they need to navigate these Linux-based systems to analyze logs and investigate security incidents."

### What is the difference between > and >>?

> "The single `>` operator redirects output and completely overwrites the target file, while the double `>>` operator appends the output to the end of the file, preserving the original data."

### How do you search for a file in Linux?

> "You use the `find` command, specifying where to search and the file name. For example: `find /home -name config.txt` searches the home directory for that specific file."

### What does grep do? Give one example.

> "Grep searches through text files for specific keywords and prints out the matching lines. For example, running `grep "accepted" auth.log` will instantly display all successful login entries inside that log file."

### Which command shows your current directory?

> "The `pwd` command, which stands for Print Working Directory, displays the absolute folder path of where you are currently working."
