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
