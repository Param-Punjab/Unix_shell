## Downloading  VirtualBox

- To download VirtualBox, go to the official site virtualbox.org and download the latest version for windows.
  ![How to download virtual box](https://media.geeksforgeeks.org/wp-content/uploads/20200123114435/VirtualBox-Windows-Download.png)

## Beginning with the Installation:  
- Getting Started:
![Error 404](https://media.geeksforgeeks.org/wp-content/uploads/20200123114440/VirtualBox-Windows-Installation-01.png)

- Select Installation Location:
![Error 404](https://media.geeksforgeeks.org/wp-content/uploads/20200123114443/VirtualBox-Windows-Installation-02.png)
  
- Creating Entries and Shortcuts:
![Error 404](https://media.geeksforgeeks.org/wp-content/uploads/20200123114446/VirtualBox-Windows-Installation-03.png)

- Ready to Install:
![Error 404](https://media.geeksforgeeks.org/wp-content/uploads/20200123114449/VirtualBox-Windows-Installation-04.png)

- Installing Files and packages:
![Error 404](https://media.geeksforgeeks.org/wp-content/uploads/20200123114452/VirtualBox-Windows-Installation-05.png)

- Installing Certificates:
![Error 404](https://media.geeksforgeeks.org/wp-content/uploads/20200123114456/VirtualBox-Windows-Installation-06.png)

- Finished Installation:
![Error 404](https://media.geeksforgeeks.org/wp-content/uploads/20200123114501/VirtualBox-Windows-Installation-07.png)

## When you will open virtualbox it will look like as shown below:
![Error 404](https://media.geeksforgeeks.org/wp-content/uploads/20200123114507/VirtualBox-Windows-Installation-08.png)
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

# Detailed Notes on Loops

**Last updated on 2023-11-10 | Edit this page**

---

## OVERVIEW

Loops in programming allow for the repetition of commands or sets of commands for each item in a list. This feature enhances productivity through automation by reducing the need for manual repetition and minimizing typing errors.

---

## QUESTIONS

### How can I perform the same actions on many different files?
You can use loops to apply one or more commands to each file in a set.

### Objectives
- Write a loop to apply commands to a set of files.
- Trace the values of a loop variable during loop execution.
- Understand the difference between a variable’s name and its value.
- Explain why spaces and some punctuation characters should be avoided in file names.
- Demonstrate how to view and re-run recently executed commands.

---

## Chapter : 5 LOOPS IN SHELL

### Basic Structure

A loop in shell scripting is generally used to repeat commands for each item in a list. Here’s the basic structure of a `for` loop:

```bash
for variable in list_of_items
do
    command_using $variable
done
```

- `for`: Indicates the start of the loop.
- `variable`: Holds the current item from the list in each iteration.
- `do`: Starts the block of commands to be executed for each item.
- `done`: Ends the loop.

### Example

Suppose we have several files: `basilisk.dat`, `minotaur.dat`, `unicorn.dat`. We want to print out the classification for each species (given on the second line of each file). Here’s how a loop can solve this:

```bash
for filename in basilisk.dat minotaur.dat unicorn.dat
do
    echo $filename
    head -n 2 $filename | tail -n 1
done
```

**Output:**

```plaintext
basilisk.dat
CLASSIFICATION: basiliscus vulgaris
minotaur.dat
CLASSIFICATION: bos hominus
unicorn.dat
CLASSIFICATION: equus monoceros
```

### Prompt Behavior

- The shell prompt changes from `$` to `>` to indicate that a multi-line command is being entered.
- The `;` can be used to separate commands on a single line.

### Variable Expansion

Inside a loop, the `$` symbol is used to refer to the value of a variable. For instance, `$filename` gets replaced with the current filename during each iteration.

### Naming Variables

- **Good Practice:** Use meaningful names (e.g., `filename`).
- **Avoid:** Using generic names like `x` or misleading names like `temperature`.

### Looping Over Different Lists

Loops can handle different types of lists, including filenames, numbers, or other data subsets.

---

## VARIABLES IN LOOPS

### Loop Over File Extensions

Example: Listing files with `.pdb` extension:

```bash
for datafile in *.pdb
do
    ls $datafile
done
```

- **First Loop:** `ls *.pdb` lists all `.pdb` files in each iteration.
- **Second Loop:** `ls $datafile` lists individual files, expanding each file’s name.

### Limiting Sets of Files

To limit the files processed:

```bash
for filename in c*
do
    ls $filename
done
```

- **Output:** Only files starting with `c` are listed.

Using wildcards like `*c*` can match different patterns:

```bash
for filename in *c*
do
    ls $filename
done
```

- **Output:** Matches files with `c` anywhere in the name.

---

## SAVING TO A FILE IN A LOOP

### Part One

If you save the content of each file into `alkanes.pdb`:

```bash
for alkanes in *.pdb
do
    echo $alkanes
    cat $alkanes > alkanes.pdb
done
```

- **Result:** Only the content from the last file (`propane.pdb`) is saved to `alkanes.pdb`.

### Part Two

Appending content to `all.pdb`:

```bash
for datafile in *.pdb
do
    cat $datafile >> all.pdb
done
```

- **Result:** All `.pdb` file contents are concatenated and saved to `all.pdb`.

---

## MORE COMPLEX EXAMPLES

### Example Loop

To select lines 81-100 from each file:

```bash
for filename in *.dat
do
    echo $filename
    head -n 100 $filename | tail -n 20
done
```

- **Purpose:** Prints filenames and specific lines from each file.

### Handling Spaces in Filenames

For filenames with spaces, use quotes:

```bash
for filename in "red dragon.dat" "purple unicorn.dat"
do
    head -n 100 "$filename" | tail -n 20
done
```

- **Without Quotes:** Errors occur due to spaces being treated as delimiters.

### Backing Up Files

To copy files with a prefix:

```bash
for filename in *.dat
do
    cp $filename original-$filename
done
```

- **Purpose:** Creates backup copies with the prefix `original-`.

---

## NELLE’S PIPELINE: PROCESSING FILES

Nelle builds up commands for processing data files with `goostats.sh`. She uses history commands and arrow keys to edit and re-run previous commands.

### Using History Commands

- **`history`**: Displays recent commands.
- **`!number`**: Repeats a command by number.
- **`!!`**: Repeats the last command.
- **`!$`**: Refers to the last argument of the previous command.
- **Ctrl+R**: Searches command history.

### Example with `goostats.sh`

```bash
for datafile in NENE*A.txt NENE*B.txt
do
    bash goostats.sh $datafile stats-$datafile
done
```

- **Result:** Processes files and generates corresponding output filenames.

---

## KEY POINTS

- **For Loops:** Repeat commands for each item in a list.
- **Variables:** Use `$variable` to expand variable values.
- **File Names:** Avoid spaces and special characters to simplify variable expansion.
- **History Commands:** Use history and shortcuts to repeat or search previous commands.
- **Dry Runs:** Echo commands to preview what would be executed without running them.

---

These notes cover the essentials of loops, their usage, and practical examples to enhance your shell scripting skills.

# Chapter : 6 Shell Scripts

**Last updated on 2023-08-05**

---

#### Overview

Shell scripts are a powerful way to automate repetitive tasks by saving a series of commands in a file. This file can then be executed to run the commands as a program. Shell scripts enhance efficiency, accuracy, and reproducibility, making them a valuable tool for managing command-line operations.

#### Objectives

1. **Write a shell script to execute commands on a fixed set of files.**
2. **Run a shell script from the command line.**
3. **Create a script that operates on files specified by the user.**
4. **Incorporate shell scripts into pipelines for more complex operations.**

#### Creating and Running a Shell Script

1. **Creating a Basic Script**

   Start by creating a new file called `middle.sh` in the `alkanes/` directory:

   ```bash
   $ cd alkanes
   $ nano middle.sh
   ```

   Insert the following line into `middle.sh`:

   ```bash
   head -n 15 octane.pdb | tail -n 5
   ```

   Save the file (Ctrl-O) and exit (Ctrl-X). Execute the script with:

   ```bash
   $ bash middle.sh
   ```

   This command will output lines 11 to 15 from `octane.pdb`.

2. **Using Variables in Scripts**

   To make the script more flexible, edit `middle.sh` to use a variable for the filename:

   ```bash
   $ nano middle.sh
   head -n 15 "$1" | tail -n 5
   ```

   Run the script with:

   ```bash
   $ bash middle.sh octane.pdb
   ```

   You can now use different filenames:

   ```bash
   $ bash middle.sh pentane.pdb
   ```

3. **Handling Multiple Arguments**

   Modify `middle.sh` to handle additional arguments for line ranges:

   ```bash
   $ nano middle.sh
   head -n "$2" "$1" | tail -n "$3"
   ```

   Run the script with:

   ```bash
   $ bash middle.sh pentane.pdb 15 5
   ```

   This will extract lines 15 through 19 from `pentane.pdb`.

4. **Adding Comments**

   Improve readability by adding comments at the top of `middle.sh`:

   ```bash
   $ nano middle.sh
   # Select lines from the middle of a file.
   # Usage: bash middle.sh filename end_line num_lines
   head -n "$2" "$1" | tail -n "$3"
   ```

#### Advanced Scripting Techniques

1. **Processing Multiple Files**

   Create a script `sorted.sh` to sort files by their length:

   ```bash
   $ nano sorted.sh
   # Sort files by their length.
   # Usage: bash sorted.sh one_or_more_filenames
   wc -l "$@" | sort -n
   ```

   Run the script with:

   ```bash
   $ bash sorted.sh *.pdb ../creatures/*.dat
   ```

2. **Listing Unique Species**

   Write `species.sh` to list unique species from multiple files:

   ```bash
   $ nano species.sh
   # List unique species from files.
   # Usage: bash species.sh filename1 filename2 ...
   cut -d , -f 2 "$@" | sort | uniq
   ```

   Run the script with:

   ```bash
   $ bash species.sh animals.csv
   ```

3. **Re-creating Commands from History**

   Save recent commands to a script:

   ```bash
   $ history | tail -n 5 > redo-figure-3.sh
   ```

   Edit `redo-figure-3.sh` to remove history command numbers and extra lines.

#### Handling Script Errors

1. **Debugging Scripts**

   If a script produces no output, use the `-x` option to debug:

   ```bash
   $ bash -x do-errors.sh NENE*A.txt NENE*B.txt
   ```

   The `-x` option will show the commands being executed, helping to identify errors.

#### Key Points

- **Saving Commands**: Store frequently used commands in shell scripts for easy re-use.
- **Running Scripts**: Execute scripts using `bash [filename]`.
- **Arguments**: Use `$@` for all command-line arguments and `$1`, `$2`, etc., for specific arguments.
- **Quoting Variables**: Always quote variables to handle spaces in filenames and other arguments.
- **Flexibility**: Allow users to specify files or parameters to increase script versatility.

Shell scripts can greatly streamline workflows, making repetitive tasks more efficient and less prone to errors. By leveraging the power of scripting, you can automate complex operations and ensure consistency in your command-line tasks.

# Chapter : 7 Finding Things

### Overview
This guide explains how to find files and lines within files using Unix commands. It covers the use of `grep` to search for patterns in text files and `find` to locate files and directories. It also discusses combining command outputs and handling different types of files, including binary files.

---

### Grep: Finding Lines in Files

#### Introduction
`grep` (Global Regular Expression Print) is a command-line utility used to search for lines in files that match a specified pattern. It is highly versatile and can handle a variety of search options.

#### Basic Usage
To search for a pattern in a file:
```bash
grep pattern filename
```

#### Examples
1. **Simple Pattern Search:**
   ```bash
   $ grep not haiku.txt
   OUTPUT
   Is not the true Tao, until
   "My Thesis" not found
   Today it is not working
   ```

2. **Word Boundary Search:**
   To search for a whole word, use the `-w` option:
   ```bash
   $ grep -w The haiku.txt
   OUTPUT
   The Tao that is seen
   ```

3. **Case Insensitive Search:**
   To make the search case-insensitive, use the `-i` option:
   ```bash
   $ grep -n -w -i "the" haiku.txt
   OUTPUT
   1:The Tao that is seen
   2:Is not the true Tao, until
   6:and the presence of absence:
   ```

4. **Inverting Search:**
   To find lines that do not match the pattern, use the `-v` option:
   ```bash
   $ grep -n -w -v "the" haiku.txt
   OUTPUT
   1:The Tao that is seen
   3:You bring fresh toner.
   5:With searching comes loss
   7:"My Thesis" not found.
   9:Yesterday it worked
   10:Today it is not working
   11:Software is like that.
   ```

5. **Recursive Search:**
   To search for a pattern in files within subdirectories, use the `-r` option:
   ```bash
   $ grep -r Yesterday .
   OUTPUT
   ./LittleWomen.txt:"Yesterday, when Aunt was asleep and I was trying to be as still as a
   ./LittleWomen.txt:Yesterday at dinner, when an Austrian officer stared at us and then
   ./LittleWomen.txt:Yesterday was a quiet day spent in teaching, sewing, and writing in my
   ./haiku.txt:Yesterday it worked
   ```

#### Advanced Patterns
1. **Using Wildcards (Regular Expressions):**
   To find lines with an ‘o’ in the second position:
   ```bash
   $ grep -E "^.o" haiku.txt
   OUTPUT
   You bring fresh toner.
   Today it is not working
   Software is like that.
   ```

2. **Combining Commands:**
   Using `find` with `grep`:
   ```bash
   $ grep "searching" $(find . -name "*.txt")
   OUTPUT
   ./writing/LittleWomen.txt:sitting on the top step, affected to be searching for her book, but was
   ./writing/haiku.txt:With searching comes loss
   ```

---

### Find: Locating Files and Directories

#### Introduction
`find` is a command-line utility used to search for files and directories that match specified criteria.

#### Basic Usage
To search for files or directories:
```bash
find path criteria
```

#### Examples
1. **Find All Files and Directories:**
   ```bash
   $ find .
   OUTPUT
   .
   ./writing
   ./writing/LittleWomen.txt
   ./writing/haiku.txt
   ./creatures
   ./creatures/basilisk.dat
   ./creatures/unicorn.dat
   ./creatures/minotaur.dat
   ./animal-counts
   ./animal-counts/animals.csv
   ./numbers.txt
   ./alkanes
   ./alkanes/ethane.pdb
   ./alkanes/propane.pdb
   ./alkanes/octane.pdb
   ./alkanes/pentane.pdb
   ./alkanes/methane.pdb
   ./alkanes/cubane.pdb
   ```

2. **Find Only Directories:**
   ```bash
   $ find . -type d
   OUTPUT
   .
   ./writing
   ./creatures
   ./animal-counts
   ./alkanes
   ```

3. **Find Only Files:**
   ```bash
   $ find . -type f
   OUTPUT
   ./writing/LittleWomen.txt
   ./writing/haiku.txt
   ./creatures/basilisk.dat
   ./creatures/unicorn.dat
   ./creatures/minotaur.dat
   ./animal-counts/animals.csv
   ./numbers.txt
   ./alkanes/ethane.pdb
   ./alkanes/propane.pdb
   ./alkanes/octane.pdb
   ./alkanes/pentane.pdb
   ./alkanes/methane.pdb
   ./alkanes/cubane.pdb
   ```

4. **Find Files by Name:**
   ```bash
   $ find . -name "*.txt"
   OUTPUT
   ./writing/LittleWomen.txt
   ./writing/haiku.txt
   ./numbers.txt
   ```

#### Combining Find with Other Commands
1. **Count Lines in Files Found by Find:**
   ```bash
   $ wc -l $(find . -name "*.txt")
   OUTPUT
   21022 ./writing/LittleWomen.txt
   11 ./writing/haiku.txt
   5 ./numbers.txt
   21038 total
   ```

2. **Find Files and Count Lines with `grep` and `find`:**
   ```bash
   $ grep "searching" $(find . -name "*.txt")
   OUTPUT
   ./writing/LittleWomen.txt:sitting on the top step, affected to be searching for her book, but was
   ./writing/haiku.txt:With searching comes loss
   ```

---

### Handling Binary Files

#### Introduction
Binary files contain data in formats other than text. `grep` is designed for text and may not work well with binary files. For binary files, it’s often necessary to convert or extract text-like elements.

#### Examples
1. **Convert Binary Data to Text:**
   Tools like `strings` can be used to extract printable text from binary files:
   ```bash
   strings binaryfile | grep pattern
   ```

2. **Limitations:**
   Complex data extraction from formats like spreadsheets or images may require specialized tools or programming languages.

---

### Key Points
- **`find`**: Finds files with specific properties matching patterns.
- **`grep`**: Finds lines in files that match patterns.
- **`--help`**: Displays usage information for many commands.
- **`man [command]`**: Shows the manual page for a given command.
- **`$([command])`**: Inserts the output of a command into another command.

Feel free to ask if you need more details on any of these topics!
