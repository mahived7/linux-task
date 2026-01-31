# Linux Environment Setup & Exploration

## Project Overview
This repository documents my completion of Task 1: Linux Environment Setup & Exploration, covering fundamental Linux commands, directory navigation, file management, permissions, and system monitoring.

---

## Table of Contents
- [Tools Used](#tools-used)
- [Task Objectives](#task-objectives)
- [Step-by-Step Implementation](#step-by-step-implementation)
- [Command Reference](#command-reference)
- [Screenshots](#screenshots)
- [Key Learnings](#key-learnings)
- [Deliverables](#deliverables)

---

## Tools Used

**Primary Environment:**
- Ubuntu (Local/VM)

**Alternative Options:**
- WSL (Windows Subsystem for Linux)
- Amazon Linux (EC2 Free Tier)
- Fedora

---

## Task Objectives

The main goal of this task was to become confident in navigating and managing Linux systems through hands-on practice with:
1. Terminal access and basic navigation
2. Directory structure exploration
3. File and directory creation/manipulation
4. File viewing and editing
5. Permission management
6. System monitoring

---

## Step-by-Step Implementation

### 1. Install Ubuntu Linux & Terminal Access

**Installation Steps:**
```bash
# For WSL on Windows (PowerShell as Administrator)
wsl --install

# Verify installation
wsl --version
```

**Screenshots:**
- Installation process
- First terminal login

---

### 2. Explore Directory Structure

**Commands Used:**
```bash
# Check current directory
pwd

# List files and directories
ls
ls -l          # Long format with details
ls -la         # Include hidden files
ls -lh         # Human-readable file sizes

# Navigate to root directory
cd /
ls

# Explore system directories
ls /bin        # Binary executables
ls /etc        # Configuration files
ls /home       # User home directories
ls /var        # Variable data (logs, etc.)

# Return to home directory
cd ~
pwd
```

**Output Examples:**
```
/home/username

drwxr-xr-x 2 user user 4096 Jan 31 10:30 Desktop
drwxr-xr-x 2 user user 4096 Jan 31 10:30 Documents
drwxr-xr-x 2 user user 4096 Jan 31 10:30 Downloads
```

**Screenshots:**
- Root directory structure (`/`)
- Home directory contents
- Different `ls` command outputs

---

### 3. Create Directories and Files

**Directory Creation:**
```bash
# Create single directory
mkdir test_directory

# Create multiple directories
mkdir dir1 dir2 dir3

# Create nested directories (parent and child)
mkdir -p parent/child/grandchild

# Verify creation
ls -R parent/
```

**File Creation:**
```bash
# Create empty files using touch
touch file1.txt
touch file2.txt file3.txt

# Create file with content using echo
echo "Hello Linux!" > greeting.txt

# Verify files created
ls -l
```

**Removal Operations:**
```bash
# Remove single file
rm file1.txt

# Remove multiple files
rm file2.txt file3.txt

# Remove empty directory
rmdir dir1

# Remove directory with contents
rm -r parent/

# Remove with confirmation prompt
rm -i greeting.txt

# Verify removal
ls
```

**Screenshots:**
- Directory creation with `mkdir -p`
- File creation with `touch`
- Directory removal with `rm -r`

---

### 4. File Viewing and Editing

**Viewing Files:**
```bash
# Display entire file content
cat filename.txt

# View file with pagination (scroll with arrows, q to quit)
less filename.txt

# Display first 10 lines
head filename.txt

# Display last 10 lines
tail filename.txt

# Display first 20 lines
head -n 20 filename.txt

# Follow file updates in real-time (useful for logs)
tail -f logfile.txt
```

**Editing Files:**

**Using nano (beginner-friendly):**
```bash
nano myfile.txt

# Keyboard shortcuts in nano:
# Ctrl + O : Save file
# Ctrl + X : Exit
# Ctrl + K : Cut line
# Ctrl + U : Paste
```

**Using vim:**
```bash
vim myfile.txt

# Vim modes:
# Press 'i' : Insert mode (start typing)
# Press 'Esc' : Command mode
# Type ':w' : Save
# Type ':q' : Quit
# Type ':wq' : Save and quit
# Type ':q!' : Quit without saving
```

**Screenshots:**
- `cat` command output
- `nano` editor interface
- `vim` editor interface

---

### 5. File Permissions Management

**Understanding Permissions:**
```
-rwxr-xr-x
 │││││││││
 ││││││││└─ Others: execute
 │││││││└── Others: write
 ││││││└─── Others: read
 │││││└──── Group: execute
 ││││└───── Group: write
 │││└────── Group: read
 ││└─────── Owner: execute
 │└──────── Owner: write
 └───────── Owner: read
```

**Viewing Permissions:**
```bash
# List files with permissions
ls -l

# Example output:
# -rw-r--r-- 1 user group 1234 Jan 31 10:30 file.txt
```

**Changing Permissions with chmod:**
```bash
# Numeric method (octal)
chmod 755 script.sh    # rwxr-xr-x
chmod 644 file.txt     # rw-r--r--
chmod 777 file.txt     # rwxrwxrwx (full permissions)

# Symbolic method
chmod +x script.sh     # Add execute permission
chmod -w file.txt      # Remove write permission
chmod u+x file.txt     # Add execute for user
chmod g-w file.txt     # Remove write for group
chmod o+r file.txt     # Add read for others

# Recursive permission change
chmod -R 755 directory/
```

**Permission Numbers:**
- 4 = read (r)
- 2 = write (w)
- 1 = execute (x)
- 7 = rwx (4+2+1)
- 6 = rw- (4+2)
- 5 = r-x (4+1)

**Changing Ownership:**
```bash
# Change owner
sudo chown username file.txt

# Change owner and group
sudo chown username:groupname file.txt

# Change recursively
sudo chown -R username:groupname directory/
```

**Screenshots:**
- `ls -l` showing permissions
- Permission changes with `chmod`
- Before and after permission modifications

---

### 6. System Monitoring

**Process Monitoring:**
```bash
# Display running processes (press q to quit)
top

# Better alternative to top (may need installation)
htop

# Install htop if not available
sudo apt update
sudo apt install htop
```

**Disk Usage:**
```bash
# Show disk space usage
df -h

# Show directory size
du -sh /path/to/directory

# Show sizes of all items in current directory
du -h --max-depth=1
```

**Memory Usage:**
```bash
# Display memory usage
free -m        # In megabytes
free -h        # Human-readable format
```

**System Information:**
```bash
# Display system information
uname -a

# CPU information
lscpu

# Check uptime
uptime
```

**Screenshots:**
- `top` command output
- `htop` interface
- `df -h` disk usage
- `free -h` memory usage

---

## Command Reference

### Navigation Commands
| Command | Description | Example |
|---------|-------------|---------|
| `pwd` | Print working directory | `pwd` |
| `cd` | Change directory | `cd /home` |
| `cd ~` | Go to home directory | `cd ~` |
| `cd ..` | Go up one directory | `cd ..` |
| `cd -` | Go to previous directory | `cd -` |

### File & Directory Commands
| Command | Description | Example |
|---------|-------------|---------|
| `ls` | List files | `ls -la` |
| `mkdir` | Create directory | `mkdir newfolder` |
| `touch` | Create empty file | `touch file.txt` |
| `rm` | Remove file | `rm file.txt` |
| `rmdir` | Remove empty directory | `rmdir folder` |
| `rm -r` | Remove directory with contents | `rm -r folder` |
| `cp` | Copy files | `cp file.txt backup.txt` |
| `mv` | Move/rename files | `mv old.txt new.txt` |

### File Viewing Commands
| Command | Description | Example |
|---------|-------------|---------|
| `cat` | Display file content | `cat file.txt` |
| `less` | View file with pagination | `less file.txt` |
| `head` | Show first lines | `head -n 10 file.txt` |
| `tail` | Show last lines | `tail -n 10 file.txt` |

### Permission Commands
| Command | Description | Example |
|---------|-------------|---------|
| `chmod` | Change permissions | `chmod 755 file.txt` |
| `chown` | Change owner | `chown user:group file.txt` |

### System Monitoring Commands
| Command | Description | Example |
|---------|-------------|---------|
| `top` | Process monitor | `top` |
| `htop` | Interactive process viewer | `htop` |
| `df` | Disk space | `df -h` |
| `free` | Memory usage | `free -m` |
| `ps` | Process status | `ps aux` |

---

## Screenshots

All screenshots are organized in the `/screenshots` directory:

```
screenshots/
├── 01-installation.png
├── 02-terminal-first-login.png
├── 03-directory-structure.png
├── 04-ls-commands.png
├── 05-mkdir-touch.png
├── 06-file-operations.png
├── 07-cat-output.png
├── 08-nano-editor.png
├── 09-vim-editor.png
├── 10-permissions-ls.png
├── 11-chmod-example.png
├── 12-top-command.png
├── 13-htop-interface.png
├── 14-df-output.png
└── 15-free-memory.png
```

### Example Screenshots

**Directory Structure:**
![Directory Structure](screenshots/03-directory-structure.png)

**File Permissions:**
![File Permissions](screenshots/10-permissions-ls.png)

**System Monitoring:**
![Top Command](screenshots/12-top-command.png)

---

## Key Learnings

### 1. Linux File System Hierarchy
- `/` - Root directory (top of filesystem)
- `/home` - User home directories
- `/bin` - Essential binary executables
- `/etc` - Configuration files
- `/var` - Variable data (logs, temporary files)
- `/tmp` - Temporary files

### 2. Permission System
- Three permission types: Read (r), Write (w), Execute (x)
- Three user categories: Owner, Group, Others
- Numeric representation makes bulk changes easier
- Execute permission required to run scripts

### 3. Command Efficiency
- Tab completion saves time
- Arrow keys recall command history
- `man` command provides detailed documentation
- Combining commands with pipes (`|`) increases productivity

### 4. Best Practices
- Always verify before using `rm -rf`
- Use `ls` to confirm operations
- Regular backups with `cp` before major changes
- Check permissions before executing scripts

---

## Deliverables

✅ **Command Log File** - Complete history of all commands used

✅ **Screenshots** - Visual documentation of terminal usage and outputs

✅ **Summary Markdown Document** - This comprehensive README file

---

## Final Outcome

Successfully completed all task objectives and achieved confidence in:
- Navigating Linux file systems efficiently
- Managing files and directories safely
- Understanding and modifying file permissions
- Monitoring system resources
- Using text editors for file manipulation

---

## Author

**Name:** [Your Name]  
**Date:** January 31, 2026  
**Task:** Linux Environment Setup & Exploration

---

## Additional Resources

- [Linux Command Line Basics](https://ubuntu.com/tutorials/command-line-for-beginners)
- [Linux File Permissions Guide](https://www.linux.com/training-tutorials/understanding-linux-file-permissions/)
- [Vim Cheat Sheet](https://vim.rtorr.com/)
- [Linux Man Pages](https://man7.org/linux/man-pages/)

---

## License

This project is for educational purposes as part of DevOps training.
