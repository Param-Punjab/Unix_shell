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
- A few essential commands can accomplish a lot.

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
