# Chapter 1: Introducing the Shell

## Overview

### Questions
- What is a command shell and why would I use one?

### Objectives
- Explain how the shell relates to the keyboard, the screen, the operating system, and users' programs.
- Explain when and why command-line interfaces should be used instead of graphical interfaces.

## Background
Humans and computers interact in various ways, such as through:
- Keyboard and mouse
- Touch screen interfaces
- Speech recognition systems

### Graphical User Interface (GUI)
- The most widely used method to interact with personal computers.
- Uses menu-driven interactions and mouse clicks.
- Intuitive but scales poorly for repetitive tasks.

### Command-Line Interface (CLI)
- Uses text-based commands.
- Scales well for repetitive tasks.

### Example
Using a GUI to copy the third line of 1000 text files in different directories is time-consuming and error-prone. The Unix shell, a CLI, can automate and speed up this process.

## The Shell
- A program where users type commands.
- Can invoke complex programs or simple commands.
- Popular Unix shell: Bash (Bourne Again SHell).
- Git Bash: Allows Windows users to use a Bash-like interface with Git.

### Learning the Shell
- Requires time and effort.
- Unlike a GUI, CLI requires learning specific commands.
- A few essential commands can achieve a lot.

### Advantages of the Shell
- Combines existing tools into powerful pipelines.
- Handles large volumes of data automatically.
- Scripts improve workflow reproducibility.
- Easier interaction with remote machines and supercomputers.
- Essential for specialized tools and high-performance computing.

## Getting Started with the Shell

### The Prompt
- Indicates the shell is waiting for input.
- Usually represented by `$`.
- Do not type the `$` when entering commands.
- The cursor indicates the typing position.

### Example
```bash
$ ls
```
- Lists contents of the current directory.
- If a command is not found, an error message is displayed.

### Common Error
```bash
$ ks
ks: command not found
```
- Occurs if the command is mistyped or not installed.

## Nelle's Pipeline: A Typical Problem
Nelle Nemo, a marine biologist, needs to process 1520 samples using an imaginary program `goostats.sh`.

### Problem
- Running `goostats.sh` by hand using a GUI takes over 12 hours.
- Using the shell, Nelle can automate this task and focus on writing her paper.

### Skills Nelle Needs
- Navigate to a file/directory
- Create a file/directory
- Check the length of a file
- Chain commands together
- Retrieve a set of files
- Iterate over files
- Run a shell script containing her pipeline

## Key Points
- A shell reads commands and runs other programs.
- This lesson uses Bash, the default shell in many Unix implementations.
- Programs run in Bash by entering commands at the command-line prompt.
- The shell has a high action-to-keystroke ratio, supports automating repetitive tasks, and accesses networked machines.
- A significant challenge is knowing which commands to run and how to run them.


# Chapter 2: Navigating Files and Directories

## Questions

1. **How can I move around on my computer?**
2. **How can I see what files and directories I have?**
3. **How can I specify the location of a file or directory on my computer?**

## Objectives

1. Explain the similarities and differences between a file and a directory.
2. Translate an absolute path into a relative path and vice versa.
3. Construct absolute and relative paths that identify specific files and directories.
4. Use options and arguments to change the behavior of a shell command.
5. Demonstrate the use of tab completion and explain its advantages.

## Key Concepts

- **File System:** Manages files and directories. Files hold information, and directories (folders) hold files or other directories.
- **pwd (print working directory):** Shows the current directory.
- **ls (list):** Lists the contents of a directory.
- **cd (change directory):** Changes the current directory.

## Commands Overview

1. **pwd**
   - Shows the current working directory.
   - Example: `$ pwd` might output `/Users/nelle`.

2. **ls**
   - Lists the contents of the current directory.
   - Example: `$ ls` might output:
     ```
     Applications Documents Library Music Public
     Desktop Downloads Movies Pictures
     ```
   - Options:
     - `-F`: Classifies the output by adding markers to file and directory names.
       - `/` indicates a directory.
       - `@` indicates a link.
       - `*` indicates an executable.

3. **cd**
   - Changes the current working directory.
   - Example: `$ cd Desktop` moves to the Desktop directory.

## The File System Structure

- **Root Directory:** The topmost directory, represented by `/`.
- **Home Directory:** User's personal directory, e.g., `/Users/nelle`.
- **Navigating the File System:**
  - **Absolute Path:** Specifies a location from the root directory (e.g., `/Users/nelle/Desktop`).
  - **Relative Path:** Specifies a location starting from the current directory (e.g., `Desktop/shell-lesson-data`).

## Examples

### Moving Around the File System

1. **Finding Your Location:**
   ```bash
   $ pwd
   /Users/nelle
   ```

2. **Listing Contents:**
   ```bash
   $ ls -F
   Applications/ Documents/ Library/ Music/ Public/
   Desktop/ Downloads/ Movies/ Pictures/
   ```

3. **Changing Directories:**
   ```bash
   $ cd Desktop
   $ pwd
   /Users/nelle/Desktop
   ```

4. **Moving to a Subdirectory:**
   ```bash
   $ cd shell-lesson-data/exercise-data
   $ pwd
   /Users/nelle/Desktop/shell-lesson-data/exercise-data
   ```

5. **Moving Up a Directory:**
   ```bash
   $ cd ..
   $ pwd
   /Users/nelle/Desktop/shell-lesson-data
   ```

6. **Returning to Home Directory:**
   ```bash
   $ cd
   $ pwd
   /Users/nelle
   ```

### Viewing Hidden Files

- Use `-a` option with `ls` to show hidden files:
  ```bash
  $ ls -Fa
  ./  ../  .bash_profile  Applications/  Documents/  Library/  Music/
  ```

### Getting Help

1. **Using `--help`:**
   ```bash
   $ ls --help
   ```

2. **Using `man`:**
   ```bash
   $ man ls
   ```

### Combining Options

- Combine multiple options with a single `-`:
  ```bash
  $ ls -F -a
  $ ls -Fa
  ```

### Exploring Other Directories

- List contents of another directory:
  ```bash
  $ ls -F Desktop
  shell-lesson-data/
  ```

- Navigate to a specific directory using an absolute path:
  ```bash
  $ cd /Users/nelle/Desktop/shell-lesson-data
  ```

### Shortcuts

1. **Home Directory Shortcut (`~`):**
   ```bash
   $ cd ~
   $ cd ~/Desktop
   ```

2. **Previous Directory Shortcut (`-`):**
   ```bash
   $ cd -
   ```

### Absolute vs Relative Paths

- **Absolute Path:** Starts from the root directory.
  ```bash
  $ cd /Users/nelle/Desktop
  ```

- **Relative Path:** Starts from the current directory.
  ```bash
  $ cd Desktop
  ```

### Tab Completion

- **Using Tab to Complete Commands:**
  ```bash
  $ ls nor[TAB]
  $ ls north-pacific-gyre/
  ```

## Key Points

- The file system manages information on the disk.
- Information is stored in files and directories.
- Directories can store other directories, forming a directory tree.
- `pwd` prints the current working directory.
- `ls [path]` lists a directory's contents.
- `cd [path]` changes the current directory.
- Most commands accept options that begin with a single `-`.
- Directory names in paths are separated by `/` on Unix and `\` on Windows.
- `/` alone represents the root directory.
- An absolute path starts from the root of the file system.
- A relative path starts from the current location.
- `.` means the current directory; `..` means the parent directory.

This detailed note should help you understand the basics of navigating files and directories in the shell. Practice these commands and explore your file system to become more comfortable with these concepts.

# Notes on "Working With Files and Directories"

### Overview
- **Key Questions:**
  1. How can I create, copy, and delete files and directories?
  2. How can I edit files?
- **Objectives:**
  1. Create a directory hierarchy that matches a given diagram.
  2. Create files in that hierarchy using an editor or by copying and renaming existing files.
  3. Delete, copy, and move specified files and/or directories.

### Creating Directories
- **Checking Current Directory:**
  ```bash
  $ pwd
  /Users/nelle/Desktop/shell-lesson-data
  ```

- **Navigating to a Directory:**
  ```bash
  $ cd exercise-data/writing/
  $ ls -F
  haiku.txt  LittleWomen.txt
  ```

- **Creating a New Directory:**
  ```bash
  $ mkdir thesis
  $ ls -F
  haiku.txt  LittleWomen.txt  thesis/
  ```

- **Creating Nested Directories:**
  ```bash
  $ mkdir -p ../project/data ../project/results
  $ ls -FR ../project
  ../project/:
  data/  results/
  ../project/data:
  ../project/results:
  ```

### Good Naming Practices for Files and Directories
- **Avoid spaces**: Use `-` or `_` instead.
- **Do not begin with `-`**: Commands treat names starting with `-` as options.
- **Use letters, numbers, `.`, `-`, and `_`**: Avoid special characters unless necessary.
- **Referencing Special Names**: Surround names with spaces or special characters in single quotes (`'`).

### Creating Text Files
- **Changing Directory and Using a Text Editor:**
  ```bash
  $ cd thesis
  $ nano draft.txt
  ```
- **Saving and Exiting in Nano:**
  - Save: `Ctrl + O`, then `Enter`.
  - Exit: `Ctrl + X`.

- **Creating Files with `touch`:**
  ```bash
  $ touch my_file.txt
  $ ls -l my_file.txt
  $ rm my_file.txt
  ```

### Naming Conventions
- Use file extensions to indicate file types (`.txt`, `.pdf`, `.cfg`, `.png`, etc.).

### Moving Files and Directories
- **Renaming Files with `mv`:**
  ```bash
  $ mv thesis/draft.txt thesis/quotes.txt
  $ ls thesis
  quotes.txt
  ```

- **Moving Files to Another Directory:**
  ```bash
  $ mv thesis/quotes.txt .
  $ ls thesis
  $ ls quotes.txt
  quotes.txt
  ```

- **Moving Files to Another Folder:**
  ```bash
  $ mv sucrose.dat maltose.dat ../raw/
  ```

### Copying Files and Directories
- **Copying Files with `cp`:**
  ```bash
  $ cp quotes.txt thesis/quotations.txt
  $ ls quotes.txt thesis/quotations.txt
  quotes.txt   thesis/quotations.txt
  ```

- **Copying Directories with `cp -r`:**
  ```bash
  $ cp -r thesis thesis_backup
  $ ls thesis thesis_backup
  thesis:
  quotations.txt
  thesis_backup:
  quotations.txt
  ```

### Removing Files and Directories
- **Deleting Files with `rm`:**
  ```bash
  $ rm quotes.txt
  $ ls quotes.txt
  ls: cannot access 'quotes.txt': No such file or directory
  ```

- **Deleting Directories with `rm -r`:**
  ```bash
  $ rm -r thesis
  ```

### Operations with Multiple Files and Directories
- **Copying Multiple Files:**
  ```bash
  $ mkdir backup
  $ cp creatures/minotaur.dat creatures/unicorn.dat backup/
  ```

- **Wildcards:**
  - `*`: Represents zero or more characters.
  - `?`: Represents exactly one character.
  - Combining Wildcards: `???ane.pdb` matches `cubane.pdb`, `ethane.pdb`, `octane.pdb`.

- **Examples of Using Wildcards:**
  ```bash
  $ ls *t*ane.pdb
  ethane.pdb methane.pdb
  ```

### Practical Exercises
- **Move and Organize Files:**
  ```bash
  $ mkdir recombined
  $ mv proteins.dat recombined/
  $ cp recombined/proteins.dat ../proteins-saved.dat
  ```

- **Back Up and Send Files:**
  ```bash
  $ cp *dataset* backup/datasets
  $ cp *calibration* backup/calibration
  $ cp 2015-11-* send_to_bob/all_november_files/
  $ cp 2015-10-23-* send_to_bob/all_datasets_created_on_a_23rd/
  ```

- **Organizing Files in Directories:**
  ```bash
  $ mv fructose.dat analyzed/
  $ mv sucrose.dat analyzed/
  ```

- **Duplicating Directory Structure:**
  ```bash
  $ mkdir 2016-05-20
  $ cd 2016-05-20
  $ mkdir data
  $ cd data
  $ mkdir raw processed
  ```

These notes should give you a solid understanding of creating, copying, moving, and deleting files and directories, as well as using wildcards and organizing files efficiently in a Unix shell environment.

### Chapter : 4 Pipes and Filters
_Last updated on 2024-04-12 | Edit this page_

---

#### Overview

**Questions:**
1. How can I combine existing commands to produce a desired output?
2. How can I show only part of the output?

**Objectives:**
1. Explain the advantage of linking commands with pipes and filters.
2. Combine sequences of commands to get new output.
3. Redirect a command’s output to a file.
4. Explain what usually happens if a program or pipeline isn’t given any input to process.

---

### Introduction

Now that we are familiar with some basic commands, we can explore one of the shell’s most powerful features: combining existing programs in new ways. We will use the `shell-lesson-data/exercise-data/alkanes` directory, which contains files in Protein Data Bank format, describing simple organic molecules.

**Example Files in Directory:**
```bash
$ ls
cubane.pdb    methane.pdb    pentane.pdb
ethane.pdb    octane.pdb     propane.pdb
```

**Word Count Command:**
```bash
$ wc cubane.pdb
```
**Output:**
```
20  156 1158 cubane.pdb
```
`wc` (word count) counts lines, words, and characters in files.

**Using Wildcards with `wc`:**
```bash
$ wc *.pdb
```
**Output:**
```
  20  156  1158  cubane.pdb
  12  84   622   ethane.pdb
   9  57   422   methane.pdb
  30  246  1828  octane.pdb
  21  165  1226  pentane.pdb
  15  111  825   propane.pdb
 107  819  6081  total
```
`wc *.pdb` shows the total count of lines in the last line.

**Displaying Only Line Counts:**
```bash
$ wc -l *.pdb
```
**Output:**
```
  20  cubane.pdb
  12  ethane.pdb
   9  methane.pdb
  30  octane.pdb
  21  pentane.pdb
  15  propane.pdb
 107  total
```
The `-l` option shows only the number of lines per file.

---

### Handling Commands Without Input

**Issue with Missing Filename:**
```bash
$ wc -l
```
If no filename is provided, `wc` waits for input from the command prompt. To exit this state, use `Ctrl+C`.

---

### Capturing Output from Commands

**Redirecting Output to a File:**
```bash
$ wc -l *.pdb > lengths.txt
```
The `>` operator redirects the output to a file. If `lengths.txt` exists, it will be overwritten.

**Displaying File Content:**
```bash
$ cat lengths.txt
```
**Output:**
```
  20  cubane.pdb
  12  ethane.pdb
   9  methane.pdb
  30  octane.pdb
  21  pentane.pdb
  15  propane.pdb
 107  total
```
`cat` displays the content of files.

**Viewing Content Page by Page:**
```bash
$ less lengths.txt
```
`less` allows scrolling through the file page by page.

---

### Filtering Output

**Using `sort` Command:**
**Example File (`numbers.txt`):**
```
10
2
19
22
6
```
**Sorting Numerically:**
```bash
$ sort -n numbers.txt
```
**Output:**
```
2
6
10
19
22
```
The `-n` option sorts numerically rather than alphanumerically.

**Sorting and Redirecting:**
```bash
$ sort -n lengths.txt > sorted-lengths.txt
$ head -n 1 sorted-lengths.txt
```
**Output:**
```
  9  methane.pdb
```
`head -n 1` shows the first line of the sorted file.

**Important Note:**
Avoid redirecting output to the same file being processed to prevent data loss.

**Appending Data:**
```bash
$ echo hello >> testfile02.txt
```
`>>` appends output to a file.

---

### Passing Output to Another Command

**Using Pipes:**
```bash
$ wc -l *.pdb | sort -n | head -n 1
```
The `|` operator pipes output from one command to another.

**Combining Commands:**
Pipes can chain multiple commands together to avoid using intermediate files.

**Example:**
```bash
$ wc -l *.pdb | sort -n | head -n 3
```
This command finds the three files with the least number of lines.

---

### Tools Designed to Work Together

Unix programs are designed to be simple and work well together using pipes and filters. Each program reads from standard input, processes the data, and writes to standard output.

**Example Pipeline:**
```bash
$ cat animals.csv | head -n 5 | tail -n 3 | sort -r > final.txt
```
Understanding what passes through each stage of the pipeline is crucial.

**Using `cut` and `uniq`:**
```bash
$ cut -d , -f 2 animals.csv | sort | uniq
```
The `cut` command extracts columns, and `uniq` removes duplicates.

**Counting Animals:**
```bash
$ cut -d, -f 2 animals.csv | sort | uniq -c
```
The `-c` option with `uniq` counts occurrences.

---

### Summary

- **`wc`**: Counts lines, words, and characters.
- **`cat`**: Displays file contents.
- **`sort`**: Sorts lines of text.
- **`head`**: Displays the first few lines.
- **`tail`**: Displays the last few lines.
- **`>`**: Redirects output to a file (overwriting).
- **`>>`**: Appends output to a file.
- **`|`**: Pipes output from one command to another.
- **Pipes and filters**: Combine simple tools to process data efficiently.

Use pipes and filters to link simple programs together, leveraging their ability to process and transform data streams.

---

Feel free to ask if you need further details or explanations!
