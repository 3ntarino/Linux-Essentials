# 🐧 Linux Essentials Reference

![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Bash](https://img.shields.io/badge/Shell_Scripting-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active_Learning-blue)

## 📺 References & Resources

This repository documents my learning notes based on the **Linux Essentials** course/playlist. 

* **Primary Source:** [linux Course In Arabic / 
Hacktivity-AR]
* **Playlist Link:** [▶️ Click here to watch the full playlist](https://youtube.com/playlist?list=PLgCu8TiZE3OZcKIqypbqIU9pG4mZjKP5C&si=jUr8IX0DdC8MjIu7)

> *Special thanks to the instructor for the great explanation.*

> **💡 Note:**
> While this content is inspired by the source above, it represents my **personal notes, practical experiments, and summarization**. It is not a direct copy-paste of the material but rather a documented effort to understand and apply the concepts in my own way.

## 🌟 Unlock the Power of the Terminal

Mastering the Command Line is not just a skill; it's a gateway to understanding how computing truly works.

Welcome to the **Linux Essentials Journey**. This repository serves as a living documentation of my path to mastering Linux. It is designed to transform complex concepts into concise, practical references. Whether you are troubleshooting a server, automating a task, or simply navigating the file system, this guide is built to be the reliable cheat sheet you need at your fingertips.

Here, we don't just memorize commands; we understand the logic behind them.

## 🗂️ Repository Structure

The content is organized by topic to make navigation easy:

| Section | Description |
| :--- | :--- |
| **01. Introduction** | History of Linux, distributions, and the shell. |
| **02. Navigation** | Moving around the file system (`pwd`, `cd`, `ls`). |
| **03. File Management** | Creating, moving, and deleting files (`touch`, `cp`, `mv`, `rm`). |
| **04. Permissions** | Understanding user rights (`chmod`, `chown`, `sudo`). |
| **05. Text Processing** | Manipulation and searching (`cat`, `grep`, `head`, `tail`). |
| **06. User Management** | Managing users and groups. |
| **07. Scripting Basics** | Introduction to Bash scripting and automation. |

## 🚀 How to Use

You can use this repository as a cheat sheet. If you need to find how to use a specific command, simply navigate to the relevant folder or search the repository.

---

## 📚 A Note on Documentation

> **💡 Important Note:**
> This repository is a **curated reference** of the most essential commands and flags used in daily tasks. It is **not** an exhaustive encyclopaedia of every single option available in Linux.

If you want to dive deeper into any tool or command mentioned here, use the built-in **Manual** pages.

### How to use `man`:
To read the full documentation of any command, simply type `man` followed by the command name in your terminal.

```bash
man [command_name]
```

**Example:**
```bash
man ls      # Opens the manual for the 'ls' command
```

**Navigation Shortcuts:**
* **Scroll:** Use the `Up` and `Down` arrow keys (or `Space` for a full page).
* **Search:** Press `/`, type your search term, and hit Enter.
* **Exit:** Press `q` to quit the manual and go back to the terminal.

---

# 01. Introduction to Linux

Before diving into commands, it is crucial to understand what Linux is, where it came from, and how we interact with it.

## 🕰️ 1. Brief History of Linux
Linux was created in **1991** by a Finnish student named **Linus Torvalds**. He wanted to create a free, open-source alternative to the MINIX operating system (which was based on Unix).

* **The Kernel:** Linus built the "Kernel" (the core of the OS that talks to hardware).
* **The GNU Project:** Around the same time, Richard Stallman and the Free Software Foundation had built many tools (compilers, text editors) but lacked a kernel.
* **The Merger:** Linux (the kernel) was combined with GNU (the tools) to form the operating system we use today, technically called **GNU/Linux**.

> *"I'm doing a (free) operating system (just a hobby, won't be big and professional like gnu)..."* — **Linus Torvalds (1991)**

---

## 📦 2. Linux Distributions (Distros)
Strictly speaking, "Linux" is just the kernel. A **Distribution (Distro)** is a complete operating system package that includes:
1.  The Linux Kernel.
2.  System Utilities (GNU tools).
3.  A Package Manager (to install software).
4.  A Desktop Environment (GUI) - optional.

### Common Families:
* **Debian Family:** Includes **Debian**, **Ubuntu**, **Kali Linux**, and **Linux Mint**. Known for stability and `.deb` packages (using `apt`).
* **Red Hat Family:** Includes **RHEL**, **Fedora**, and **CentOS**. Standard in enterprise environments, uses `.rpm` packages (using `dnf` or `yum`).
* **Arch Family:** Includes **Arch Linux** and **Manjaro**. Known for being lightweight and "rolling release" (always the newest software).

---

## 🐚 3. The Shell
The **Shell** is a program that takes commands from the keyboard and gives them to the operating system to perform. It is the interface between the **User** and the **Kernel**.

* **CLI vs. GUI:** While Windows/macOS rely heavily on the Graphical User Interface (GUI), Linux power users rely on the Command Line Interface (CLI) via the Shell because it is faster and scriptable.
* **Bash (Bourne Again Shell):** This is the default shell for most Linux distributions.
* **The Terminal:** The window/application where you see the shell running.

### How it works:
1.  You type a command (e.g., `ls`).
2.  The Shell interprets the command.
3.   The Kernel executes it on the hardware.
4.  The output is returned to your screen.

# 02. Navigation & File System Basics

Navigating the Linux file system via the terminal is the first skill you must master. Unlike a graphical interface where you "click" folders, here you "change directories".

## 📍 1. Where am I? (`pwd`)
**pwd** stands for **P**rint **W**orking **D**irectory. It tells you exactly where you are currently located in the file system tree.

```bash
$ pwd
/home/username/Documents
```

---

## 📂 2. What is here? (`ls`)
**ls** is used to **L**i**s**t files and directories.

### Basic Usage:
```bash
ls          # Lists files in current directory (simple view)
```

### Common Flags (Options):
Flags modify how a command works.
* **`ls -l`** : Long listing format. Shows permissions, owner, size, and date.
* **`ls -a`** : All files. Shows hidden files (files starting with a dot `.`).
* **`ls -la`**: Combines both (Detailed view + Hidden files).
* **`ls -h`** : Human-readable sizes (e.g., shows 500M instead of 512000 bytes).

```bash
# Example output of 'ls -la'
drwxr-xr-x  2 user user 4096 Jan 01 10:00 .
drwxr-xr-x 20 user user 4096 Dec 31 23:59 ..
-rw-r--r--  1 user user  220 Jan 01 10:00 .bashrc
-rw-r--r--  1 user user  500 Jan 01 10:05 textfile.txt
```

---

## 🚶 3. Moving Around (`cd`)
**cd** stands for **C**hange **D**irectory. It is used to move from one folder to another.

### Absolute vs. Relative Path:
* **Absolute Path:** Starts from the root `/` (e.g., `cd /var/log`). Works from anywhere.
* **Relative Path:** Starts from where you are right now (e.g., `cd Documents`).

### Crucial Shortcuts:
| Command | Description |
| :--- | :--- |
| `cd ~` | Go to your **Home** directory (e.g., `/home/username`). |
| `cd /` | Go to the **Root** directory (the base of the system). |
| `cd ..` | Go **Up** one level (to the parent directory). |
| `cd -` | Go back to the **Previous** directory you were in. |

### Examples:
```bash
cd Documents/Work   # Enter Documents then Work
cd ..               # Go back to Documents
cd ../..            # Go back two levels
```

---

## 💡 Quick Tip: Tab Completion
You don't need to type full folder names. Type the first few letters and press **TAB**.
* If you type `cd Doc` and press **TAB**, it will autocomplete to `cd Documents/`.

# 03. File Management

Now that you know how to navigate, it's time to learn how to manipulate the files and directories themselves. This section covers creating, copying, moving, renaming, and deleting.

## 🔨 1. Creating Files and Directories

### `mkdir` (Make Directory)
Used to create new folders.
```bash
mkdir my_folder
mkdir -p project/src/assets  # Creates parent directories if they don't exist
```

### `touch` (Create Empty File)
Originally used to update file timestamps, but commonly used to create an empty file quickly.
```bash
touch index.html
touch file1.txt file2.txt file3.txt
```

---

## 📋 2. Copying (`cp`)
Used to copy files or directories from one location to another.

**Syntax:** `cp [source] [destination]`

### Copying Files:
```bash
cp file.txt backup_file.txt       # Make a copy in current dir
cp file.txt /home/user/Documents/ # Copy to another folder
```

### Copying Directories (`-r`):
To copy a folder, you MUST use the **Recursive** flag (`-r`).
```bash
cp -r folder1 folder_backup
```

---

## 🚚 3. Moving & Renaming (`mv`)
In Linux, **Moving** and **Renaming** are done with the same command: `mv`.

### Moving a file:
```bash
mv file.txt Documents/   # Moves file.txt into Documents folder
```

### Renaming a file:
If the destination is a filename (not a folder), it renames the file.
```bash
mv old_name.txt new_name.txt
```

---

## 🗑️ 4. Deleting (`rm`)
**⚠️ WARNING:** Deleting files in the terminal is permanent. There is no "Recycle Bin" or "Trash". Once it's gone, it's gone.

### Removing Files:
```bash
rm file.txt
rm -i file.txt   # Interactive mode (asks for confirmation before deleting)
```

### Removing Directories:
To delete a folder and everything inside it, use `-r` (Recursive) and `-f` (Force - strictly for no confirmation).
```bash
rmdir empty_folder      # Only works if folder is empty
rm -r my_folder         # Deletes folder and contents
rm -rf my_folder        # FORCE delete (Dangerous! Use with caution)
```

## 📝 Summary Table

| Task | Command | Example |
| :--- | :--- | :--- |
| **Create Folder** | `mkdir` | `mkdir images` |
| **Create File** | `touch` | `touch style.css` |
| **Copy File** | `cp` | `cp a.txt b.txt` |
| **Copy Folder** | `cp -r` | `cp -r src dest` |
| **Move/Rename** | `mv` | `mv old new` |
| **Delete File** | `rm` | `rm junk.txt` |
| **Delete Folder** | `rm -rf` | `rm -rf old_project` |

# 04. Linux Permissions & Ownership

Linux is a multi-user system, meaning multiple users can access the system simultaneously. To keep things secure, every file and directory has a set of **Permissions** and an **Owner**.

## 🔐 1. Understanding Permissions (`ls -l`)
When you run `ls -l`, you see a string like `-rwxr-xr--`. Let's break it down.

Structure: `[Type][Owner][Group][Others]`

| Symbol | Meaning | Value (Octal) | Description |
| :--- | :--- | :--- | :--- |
| **r** | **Read** | 4 | Can open and read the file / List directory contents. |
| **w** | **Write** | 2 | Can modify or delete the file / Create files in directory. |
| **x** | **Execute** | 1 | Can run the file as a program / Enter the directory (`cd`). |
| **-** | **No Access** | 0 | No permission granted. |

### Example Breakdown:
`drwxr-xr--`
1. **`d`**: It is a Directory (if `-` it is a file).
2. **`rwx` (Owner)**: The user who owns it can Read, Write, and Execute.
3. **`r-x` (Group)**: The group members can Read and Execute, but NOT Write.
4. **`r--` (Others)**: Everyone else can only Read.

---

## 🛡️ 2. Changing Permissions (`chmod`)
**chmod** stands for **Ch**ange **Mod**e. There are two ways to use it:

### Method A: Numeric Mode (The 4-2-1 Rule)
This method is based on **Binary Representation**. Think of permissions as 3 bits (On/Off):

| Permission | Binary | Decimal Value |
| :--- | :--- | :--- |
| **r** - - | `100` | **4** |
| - **w** - | `010` | **2** |
| - - **x** | `001` | **1** |

You simply sum up the numbers for the permissions you want:
* **7** (Full Access) = 4 + 2 + 1 (`rwx`)
* **5** (Read & Exec) = 4 + 0 + 1 (`r-x`)
* **6** (Read & Write) = 4 + 2 + 0 (`rw-`)

**Examples:**
```bash
chmod 777 script.sh   # Everyone can do everything (Dangerous!)
chmod 755 script.sh   # Owner(7), Group(5), Others(5) -> Standard for programs
chmod 644 file.txt    # Owner(rw), Group(r), Others(r) -> Standard for text files
chmod 400 key.pem     # Owner(r) only -> Very secure
```

### Method B: Symbolic Mode
Use letters to add (`+`) or remove (`-`) permissions.
* **u** (User/Owner), **g** (Group), **o** (Others), **a** (All)

```bash
chmod +x script.sh    # Make file executable for everyone
chmod u+w file.txt    # Add write permission for the User (Owner)
chmod o-r secret.txt  # Remove read permission for Others
```

---

## 👤 3. Changing Ownership (`chown`)
**chown** stands for **Ch**ange **Own**er. Only the root user (using `sudo`) can usually change ownership of files that don't belong to them.

**Syntax:** `sudo chown [user]:[group] [file]`

```bash
sudo chown ahmed file.txt          # Change owner to 'ahmed'
sudo chown ahmed:developers file.txt # Change owner to 'ahmed' and group to 'developers'
sudo chown -R ahmed /var/www/html  # Recursive (Apply to folder and everything inside)
```

---

## ⚡ 4. The Superuser (`sudo`)
**sudo** stands for **S**uper**U**ser **DO**. It gives you administrator (root) privileges for a single command.

* **Never log in as root directly.** Use `sudo` instead.
* It will ask for *your* password, not the root password.

```bash
sudo apt update       # Update system (needs root rights)
sudo reboot           # Restart the computer
```

## 🤝 Contribution
This is a personal reference, but contributions are welcome! If you spot an error or want to add a useful command shortcut:

1. Fork the repository.

2. Create a new branch (git checkout -b feature/NewTip).

3. Commit your changes.

4. Push to the branch and open a Pull Request.

## 📬 Contact
If you have any questions, suggestions, or just want to connect, feel free to reach out:

📧 Email: 3ntarino@gmail.com

