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
