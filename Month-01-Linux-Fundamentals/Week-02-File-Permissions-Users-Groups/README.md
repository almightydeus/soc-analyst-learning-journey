# Month 1: Linux Fundamentals

## Week 2: File Permissions, Users & Groups

### 1. Overview

The second week of Linux Fundamentals focused on file permissions, user accounts and groups.

Linux is a multi-user operating system in which multiple users can access and interact with system resources. To maintain security, Linux uses ownership and permission mechanisms to control who can read, modify or execute files and directories.

Understanding these mechanisms is important for system administration and cybersecurity because improperly configured permissions can expose sensitive information or allow unauthorized access to system resources.

### 2. Learning Objectives

By the end of this week, I understood how to:

- Interpret Linux file permission strings.
- Identify file owners and groups.
- Understand read, write and execute permissions.
- Modify file permissions using `chmod`.
- Change file ownership using `chown`.
- Identify users and groups on a Linux system.
- Create and manage user accounts.
- Understand the security implications of SUID permissions.

### 3. Concepts and Commands Covered

#### 3.1 Linux File Permissions

Every file in Linux has a permission structure that determines which users can access or modify it.

A typical Linux permission string looks like this:

```text
-rwxrwxrwx
```

The permission string contains ten characters.

- The first character identifies the file type.
- The remaining nine characters represent permissions assigned to three categories of users.

**Understanding the permission structure**

| Position | Description |
|---|---|
| First character | File type |
| Characters 2–4 | Owner permissions |
| Characters 5–7 | Group permissions |
| Characters 8–10 | Others permissions |

The three basic permission types are:

| Permission | Symbol | Meaning |
|---|---|---|
| Read | `r` | Allows reading file contents. |
| Write | `w` | Allows modifying file contents. |
| Execute | `x` | Allows executing a file. |

For directories, read allows listing entries, write allows modifying directory entries, and execute allows traversing or accessing entries within the directory.

#### 3.2 Viewing File Permissions

```bash
ls -la
```

This command displays detailed information about files and directories, including:

- File permissions.
- Number of links.
- File owner.
- Group ownership.
- File size.
- Modification date.
- Filename.

#### 3.3 Modifying File Permissions with chmod

The `chmod` command is used to modify file and directory permissions.

Linux supports numeric permission values:

| Permission | Numeric value |
|---|---|
| Read (`r`) | 4 |
| Write (`w`) | 2 |
| Execute (`x`) | 1 |

These values can be combined to create permission configurations.

**Example: chmod 755**

```bash
chmod 755 script.sh
```

Permission breakdown:

- Owner: 7 = read, write and execute.
- Group: 5 = read and execute.
- Others: 5 = read and execute.

Result:

```text
-rwxr-xr-x
```

**Example: chmod 644**

```bash
chmod 644 config.txt
```

Permission breakdown:

- Owner: 6 = read and write.
- Group: 4 = read only.
- Others: 4 = read only.

Result:

```text
-rw-r--r--
```

**Adding execute permission**

```bash
chmod +x script.sh
```

This adds execute permission to the file.

#### 3.4 Changing File Ownership with chown

The `chown` command changes the ownership of files and directories.

Syntax:

```bash
chown user:group file.txt
```

Example:

```bash
sudo chown bob:developers file.txt
```

This changes the file owner to `bob` and its group ownership to `developers`.

#### 3.5 Identifying SUID Files

SUID stands for Set User ID.

It is a special Linux permission that allows an executable file to run with the effective user ID of the file owner.

SUID is sometimes necessary for legitimate system operations, but incorrectly configured or vulnerable SUID executables can create privilege-escalation risks.

Command:

```bash
find / -perm -4000
```

This searches the filesystem for files with the SUID permission bit set.

From a security perspective, identifying unexpected SUID files can help analysts investigate potential privilege-escalation risks.

### 4. Users and Groups

Linux is a multi-user operating system. Each file is associated with a user owner and a group owner.

The root account is the superuser and has extensive administrative privileges.

Understanding users and groups is important when investigating unauthorized access, compromised accounts and excessive privileges.

#### 4.1 User and Group Identification Commands

| Command | Description |
|---|---|
| `whoami` | Displays the current username. |
| `id` | Displays the user's UID, GID and group memberships. |
| `groups` | Displays the groups associated with the current user. |
| `cat /etc/passwd` | Displays user account records. |
| `cat /etc/group` | Displays group information. |
| `cat /etc/shadow` | Displays password hash records; access is restricted to privileged users. |

**Understanding important Linux files**

- `/etc/passwd`: Stores user account information.
- `/etc/shadow`: Stores password hashes and related password information.
- `/etc/group`: Stores group account information.

The `/etc/shadow` file is particularly sensitive because it contains password hash information and should only be accessed by authorized privileged users.

### 5. User Management Commands

Linux provides commands for creating, modifying and deleting user accounts.

**Creating a user**

```bash
sudo adduser bob
```

Creates a new user account named `bob`.

**Setting a user's password**

```bash
sudo passwd bob
```

Allows an administrator to set or change the password for the `bob` account.

**Deleting a user**

```bash
sudo userdel bob
```

Deletes the user account named `bob`.

Note that deleting an account this way does not necessarily remove the user's home directory or all associated files.

### 6. Security Relevance

File permissions and user management are important aspects of Linux security.

Misconfigured permissions can expose sensitive files, allow unauthorized modifications or create opportunities for privilege escalation.

Examples of security concerns include:

- World-writable files that allow unauthorized users to modify content.
- Excessive permissions assigned using `chmod 777`.
- Unauthorized changes to file ownership.
- Unnecessary administrative privileges.
- Unexpected SUID executables.
- Compromised user accounts.
- Unauthorized group membership changes.

A SOC analyst should understand how to identify these conditions and investigate whether they represent a security risk.

**Common security mistake:**

```bash
chmod 777 file.txt
```

This grants read, write and execute permissions to the owner, group and everyone else.

Applying such permissions unnecessarily can expose files to unauthorized modification or execution.

### 7. Key Takeaways

This week improved my understanding of Linux access control and account management.

I learned how Linux uses ownership and permission structures to control access to files and directories. I also studied how to inspect user accounts, identify group memberships, modify permissions and manage users.

These concepts are essential for understanding Linux system security, access control and potential privilege-escalation vulnerabilities.

### 8. References

- CyberPath Academy — Month 1: Linux Fundamentals, Week 2.
- Linux manual pages: `man chmod`, `man chown`, `man find`, `man passwd`, `man adduser` and `man userdel`.
- Linux system documentation: `/etc/passwd`, `/etc/shadow` and `/etc/group`.
