# Month 1: Linux Fundamentals

## Week 1: Terminal Navigation & File Operations

### 1. Overview

The first week of Linux Fundamentals focused on understanding terminal navigation and basic file operations.

Linux provides a command-line interface (CLI) that allows users to interact with the operating system through text-based commands rather than relying entirely on a graphical interface.

Understanding terminal navigation and file management is essential for system administration and cybersecurity operations, particularly when working with Linux servers, analysing system files, and investigating security incidents.

### 2. Learning Objectives

By the end of this week, I understood how to:

- Navigate the Linux filesystem using terminal commands.
- Identify the current working directory.
- List files and directories, including hidden files.
- Move between directories.
- Create files and directories.
- Copy, move, rename and delete files.
- Use terminal shortcuts such as TAB completion.

### 3. Concepts and Commands Covered

#### 3.1 Terminal Navigation

Linux uses a hierarchical filesystem structure, with the root directory (`/`) serving as the starting point of the filesystem.

The terminal allows users to navigate this structure using commands.

| Command | Description |
|---|---|
| `pwd` | Displays the current working directory. |
| `ls` | Lists files and directories. |
| `ls -la` | Displays detailed file information, including hidden files. |
| `cd folder` | Moves into a specified directory. |
| `cd ..` | Moves one directory level backwards. |
| `cd ~` | Returns to the user's home directory. |
| `cd /` | Moves to the root directory. |
| `clear` | Clears the terminal screen. |

**Understanding hidden files**

In Linux, filenames beginning with a dot (`.`) are hidden by default.

The `ls -la` command displays these hidden files alongside ordinary files and directories.

**TAB completion**

TAB completion helps automatically complete filenames and directory paths.

Instead of manually typing an entire path, pressing the TAB key can complete the name when the match is unambiguous.

#### 3.2 File Operations

Linux provides several commands for creating, copying, moving and deleting files and directories.

| Command | Description |
|---|---|
| `mkdir logs` | Creates a directory named `logs`. |
| `touch report.txt` | Creates an empty file named `report.txt`. |
| `cp file.txt backup/` | Copies a file into the backup directory. |
| `mv file.txt docs/` | Moves a file into the docs directory. |
| `mv old.txt new.txt` | Renames a file. |
| `rm file.txt` | Deletes a file. |
| `rm -rf folder/` | Recursively deletes a directory and its contents. |

**Important distinction:**

- `cp` creates a copy of a file.
- `mv` moves or renames a file.
- `rm` removes files and does not provide a normal recycle-bin recovery mechanism.

The `rm -rf` command should be used carefully because it can permanently remove entire directory structures.

### 4. Practical Examples

The following commands demonstrate basic Linux filesystem operations.

**Example 1: Check the current location**

```bash
pwd
```

**Example 2: View files and hidden directories**

```bash
ls -la
```

**Example 3: Create a directory**

```bash
mkdir logs
```

**Example 4: Create a file**

```bash
touch report.txt
```

**Example 5: Copy a file**

```bash
mkdir backup
cp report.txt backup/
```

**Example 6: Move a file**

```bash
mkdir docs
mv report.txt docs/
```

**Example 7: Rename a file**

```bash
mv docs/report.txt docs/final-report.txt
```

**Example 8: Delete a file**

```bash
rm docs/final-report.txt
```

### 5. Relevance to Cybersecurity Operations

Terminal navigation and file operations are fundamental skills for cybersecurity analysts.

During security investigations, analysts frequently interact with Linux systems to:

- Navigate system directories.
- Locate configuration files and log files.
- Identify suspicious files and directories.
- Organize investigation evidence.
- Copy files for further examination.
- Manage files used during security investigations.

A good understanding of the Linux filesystem makes it easier to work with security tools and investigate system activity.

### 6. Key Takeaways

This week established my understanding of the Linux command-line environment and basic filesystem operations.

I learned how to navigate directories, inspect files, create and manage directories, and perform common file operations.

These commands provide the foundation for more advanced Linux administration, system monitoring and security investigations.

### 7. References

- CyberPath Academy — Month 1: Linux Fundamentals, Week 1.
- Linux manual pages: `man ls`, `man cd`, `man mkdir`, `man cp`, `man mv` and `man rm`.
