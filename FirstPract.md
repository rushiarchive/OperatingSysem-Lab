<div align="center">

# 🐧 Linux Basic Commands Practice

### A Beginner's Guide to Essential Linux Commands

![Linux](https://img.shields.io/badge/Linux-Basic_Commands-blue?style=for-the-badge&logo=linux)
![Shell](https://img.shields.io/badge/Shell-Bash-green?style=for-the-badge&logo=gnubash)
![Level](https://img.shields.io/badge/Level-Beginner-orange?style=for-the-badge)

**Author:** Shivam

</div>

---

## 📂 Table of Contents

- [📍 Working Directory](#-working-directory)
- [📁 Directory Commands](#-directory-commands)
- [📄 File Commands](#-file-commands)
- [✍️ Echo Command](#️-echo-command)
- [📋 File Operations](#-file-operations)
- [🔍 Search Commands](#-search-commands)
- [💻 System Commands](#-system-commands)
- [📖 File Viewing Commands](#-file-viewing-commands)
- [⌨️ Useful Shortcuts](#️-useful-shortcuts)
- [🚀 Practice Commands](#-practice-commands)
- [🗂️ Practice Session: Copying Files Between Directories](#️-practice-session-copying-files-between-directories)
- [📚 Quick Reference](#-quick-reference)

---

## 📍 Working Directory

### Show Current Directory

```bash
pwd
```

**Output:**

```text
/home/labex/project
```

### List Files

```bash
ls
```

**Output:**

```text
Practical  uddhav
```

---

## 📁 Directory Commands

| Command | Description |
|---|---|
| `mkdir Practical` | Create a new directory named `Practical` |
| `rmdir Practical` | Remove an **empty** directory |
| `cd uddhav` | Enter the `uddhav` directory |
| `cd ~` | Go to the home directory |
| `cd /` | Go to the root directory |
| `cd ..` | Go back one directory level |

---

## 📄 File Commands

### Create a File

```bash
touch first.txt
```

### View a File

```bash
cat first.txt
```

### Write into a File

```bash
cat > first.txt
```

Type your content, for example:

```text
hey hi this my first pract
ok
```

Then press:

```text
Ctrl + D
```

to save and exit.

### Display File Contents

```bash
cat first.txt
```

---

## ✍️ Echo Command

### Print Text to the Terminal

```bash
echo "Hello Shivam"
```

### Save Text to a File (overwrite)

```bash
echo "Hello Linux" > first.txt
```

### Append Text to a File

```bash
echo "Learning Linux" >> first.txt
```

---

## 📋 File Operations

| Command | Description |
|---|---|
| `cp first.txt second.txt` | Copy a file |
| `mv second.txt notes.txt` | Rename a file |
| `mv notes.txt uddhav/` | Move a file into a directory |
| `rm notes.txt` | Delete a file |

---

## 🔍 Search Commands

### Find a File

```bash
find . -name "first.txt"
```

### Search Text Inside a File

```bash
grep "Linux" first.txt
```

---

## 💻 System Commands

| Command | Description |
|---|---|
| `whoami` | Current user |
| `date` | Current date and time |
| `cal` | Calendar |
| `history` | Command history |
| `clear` | Clear the terminal |
| `uname -a` | System information |
| `df -h` | Disk space usage |
| `du -h` | Directory size |
| `ps` | Running processes |

---

## 📖 File Viewing Commands

| Command | Description |
|---|---|
| `head first.txt` | Show the first 10 lines |
| `tail first.txt` | Show the last 10 lines |
| `wc first.txt` | Count lines, words & characters |

---

## ⌨️ Useful Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl + C` | Stop the running command |
| `Ctrl + D` | Save file / end input |
| `Ctrl + L` | Clear the terminal |
| `Tab` | Auto-complete |
| `↑` | Previous command |
| `↓` | Next command |
| `!!` | Run the previous command |

---

## 🚀 Practice Commands

```bash
pwd
ls
mkdir Practical
rmdir Practical
touch first.txt
cat > first.txt
cat first.txt
echo "Hello Shivam"
cp first.txt second.txt
mv second.txt notes.txt
rm notes.txt
cd ~
cd /
cd ..
history
clear
```

---

## 🗂️ Practice Session: Copying Files Between Directories

This session practices creating multiple directories, creating files inside them, and copying files **between** and **into** directories using both relative and absolute paths.

### 1. Create Two Directories

```bash
mkdir batch1
mkdir batch2
```

### 2. Create Files Inside `batch1`

```bash
cd batch1
touch f1.txt
touch f2.txt
ls
```

**Output:**

```text
f1.txt  f2.txt
```

### 3. Create Files Inside `batch2`

```bash
cd ..
cd batch2
touch f3.txt
touch f4.txt
```

### 4. Copy a File From `batch1` Into `batch2` (Overwrite)

```bash
cd ..
cp batch1/f1.txt batch2/f3.txt
```

> This copies `f1.txt` from `batch1` into `batch2`, replacing `f3.txt` with its content (renaming it in the process).

### 5. Copy a File Into the Current Directory

```bash
cp batch2/f3.txt .
ls
```

**Output:**

```text
batch1  batch2  f1.txt  f2.txt  f3.txt
```

> The `.` means **"current directory."** This copies `f3.txt` into `uddhav/` while keeping its original name.

### 6. ⚠️ Common Mistake: Wrong Relative Path

```bash
cd batch1
cp uddhav/f1.txt x.txt
```

**Output:**

```text
cp: cannot stat 'uddhav/f1.txt': No such file or directory
```

> This fails because there is no `uddhav` folder **inside** `batch1`. Relative paths are resolved from the **current** directory, not from higher up the tree.

### 7. ✅ Fix: Use an Absolute Path

```bash
cp /home/labex/uddhav/f1.txt .
ls
```

**Output:**

```text
f1.txt  f2.txt
```

> Using the full absolute path (`/home/labex/uddhav/f1.txt`) works regardless of which directory you're currently in.

### 8. Copy and Rename in One Step

```bash
cp /home/labex/uddhav/f1.txt ./xyz
ls
```

**Output:**

```text
f1.txt  f2.txt  xyz
```

> `cp source destination` lets you copy **and** rename at the same time — here the copied file is saved as `xyz` instead of `f1.txt`.

### 9. Check File Details

```bash
cd ..
ls -l
```

**Output:**

```text
drwxrwxr-x 2 labex labex 45 Jul 28 14:06 batch1
drwxrwxr-x 2 labex labex 34 Jul 28 14:01 batch2
-rw-rw-r-- 1 labex labex  0 Jul 28 13:55 f1.txt
-rw-rw-r-- 1 labex labex  0 Jul 28 13:55 f2.txt
-rw-rw-r-- 1 labex labex  0 Jul 28 14:02 f3.txt
```

> `ls -l` shows permissions, owner, group, file size, and last modified time for each item.

### 💡 Key Takeaways

| Concept | Explanation |
|---|---|
| `.` (dot) | Refers to the current directory — used as a copy destination to keep the original filename |
| Relative path | Resolved from your **current** location (e.g. `batch1/f1.txt`) |
| Absolute path | Always starts with `/` and works from **anywhere** (e.g. `/home/labex/uddhav/f1.txt`) |
| `cp src dest` | Can copy **and rename** a file in a single command |
| `ls -l` | Shows detailed file info: permissions, owner, size, and timestamp |

---

## 📚 Quick Reference

| Category | Commands |
|---|---|
| Navigation | `pwd`, `ls`, `cd`, `cd ..`, `cd ~`, `cd /` |
| Directory | `mkdir`, `rmdir`, `rm -r` |
| Files | `touch`, `cat`, `cp`, `mv`, `rm` |
| Search | `find`, `grep` |
| System | `whoami`, `date`, `history`, `uname -a` |

---

<div align="center">

### ⭐ Happy Learning Linux! 🐧

If this README helped you, consider giving the repository a ⭐.

</div>
