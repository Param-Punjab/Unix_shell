# Unix_shell
### Questions

1. **How can I move around on my computer?**
2. **How can I see what files and directories I have?**
3. **How can I specify the location of a file or directory on my computer?**

### Objectives

1. **Explain the similarities and differences between a file and a directory.**
2. **Translate an absolute path into a relative path and vice versa.**
3. **Construct absolute and relative paths that identify specific files and directories.**
4. **Use options and arguments to change the behavior of a shell command.**
5. **Demonstrate the use of tab completion and explain its advantages.**

---

### Notes

#### Understanding the File System

- **File System:** Manages files and directories on the operating system.
  - **Files:** Hold information.
  - **Directories (Folders):** Hold files or other directories.

#### Commands Overview

- **pwd (Print Working Directory):** Shows the current directory.
  - **Example:**
    ```bash
    $ pwd
    /Users/nelle
    ```
- **ls (List):** Lists files and directories.
  - **Example:**
    ```bash
    $ ls
    Applications  Documents  Library  Music  Public  Desktop  Downloads  Movies  Pictures
    ```
  - **With Options:**
    ```bash
    $ ls -F
    Applications/  Documents/  Library/  Music/  Public/  Desktop/  Downloads/  Movies/  Pictures/
    ```
- **cd (Change Directory):** Changes the current directory.
  - **Example:**
    ```bash
    $ cd Desktop/shell-lesson-data/exercise-data
    ```
  - **Parent Directory:**
    ```bash
    $ cd ..
    ```
  - **Home Directory:**
    ```bash
    $ cd
    ```

#### Paths

- **Absolute Path:** Starts from the root directory (`/`).
  - **Example:**
    ```bash
    $ cd /Users/nelle/Desktop/shell-lesson-data
    ```
- **Relative Path:** Starts from the current directory.
  - **Example:**
    ```bash
    $ cd Desktop/shell-lesson-data/exercise-data
    ```

#### Special Directories

- `.`: Current directory.
- `..`: Parent directory.
- `~`: Home directory.

#### Getting Help

- **Using `--help`:**
  ```bash
  $ ls --help
  ```
- **Using `man` (manual):**
  ```bash
  $ man ls
  ```

#### Tab Completion

- **Usage:** Automatically completes directory and file names.
  - **Example:**
    ```bash
    $ ls nor<Tab>
    $ ls north-pacific-gyre/
    ```

#### Key Points

- **pwd:** Prints the current directory.
- **ls [path]:** Lists files and directories at the specified path.
- **cd [path]:** Changes the current directory.
- **Options and Arguments:**
  - **Options:** Modify the behavior of commands (e.g., `-F` for `ls`).
  - **Arguments:** Specify the target for commands (e.g., directory path).
- **Directory Separators:** `/` on Unix, `\` on Windows.
- **Root Directory:** `/`.
- **Absolute Path:** Full path from the root.
- **Relative Path:** Path from the current directory.
- **Special Symbols:**
  - `.`: Current directory.
  - `..`: Parent directory.

---

### Practical Examples

1. **Check Current Directory:**
   ```bash
   $ pwd
   /Users/nelle
   ```

2. **List Files in Current Directory:**
   ```bash
   $ ls
   ```

3. **List Files with Classification:**
   ```bash
   $ ls -F
   ```

4. **Move to a Specific Directory:**
   ```bash
   $ cd Desktop/shell-lesson-data/exercise-data
   ```

5. **Move to Parent Directory:**
   ```bash
   $ cd ..
   ```

6. **Move to Home Directory:**
   ```bash
   $ cd
   ```

7. **Use Tab Completion:**
   ```bash
   $ ls nor<Tab>
   ```

These notes and examples provide a comprehensive guide to navigating and managing files and directories in a Unix-like shell.
