# Command Log - Linux Environment Setup Task

**Date:** January 31, 2026  
**Task:** Linux Environment Setup & Exploration

---

## Session 1: Installation & Initial Setup

```bash
# Check WSL version
wsl --version

# Login to Ubuntu
wsl

# Verify user and system
whoami
uname -a
```

**Output:**
```
[Paste your actual output here]
```

---

## Session 2: Directory Exploration

```bash
# Check current directory
pwd

# List files
ls
ls -l
ls -la
ls -lh

# Navigate to root
cd /
ls

# Explore system directories
ls /bin
ls /etc
ls /home
ls /var
ls /usr

# Return to home
cd ~
pwd
```

**Output:**
```
/home/username

total 40
drwxr-xr-x 2 user user 4096 Jan 31 10:30 Desktop
drwxr-xr-x 2 user user 4096 Jan 31 10:30 Documents
drwxr-xr-x 2 user user 4096 Jan 31 10:30 Downloads
...
```

---

## Session 3: File and Directory Creation

```bash
# Create directories
mkdir test_dir
mkdir project workspace backup

# Create nested directories
mkdir -p parent/child/grandchild
mkdir -p devops/{scripts,configs,logs}

# Verify creation
ls
ls -R parent/
tree parent/  # if tree is installed

# Create files
touch file1.txt file2.txt
touch notes.md

# Create file with content
echo "This is a test file" > test.txt
echo "Hello Linux" > greeting.txt

# Verify files
ls -l
cat test.txt
```

**Output:**
```
[Paste your directory and file creation outputs]
```

---

## Session 4: File Operations

```bash
# Copy files
cp test.txt test_backup.txt
cp -r parent/ parent_backup/

# Move/Rename files
mv test.txt renamed_test.txt
mv file1.txt workspace/

# Remove files
rm file2.txt
rm -i notes.md  # with confirmation

# Remove directories
rmdir test_dir  # empty directory
rm -r parent_backup/  # with contents
rm -rf workspace/  # force remove

# Verify operations
ls -l
```

**Output:**
```
[Paste your file operation outputs]
```

---

## Session 5: File Viewing

```bash
# Create sample file with content
cat > sample.txt << EOF
Line 1: Introduction to Linux
Line 2: Basic commands
Line 3: File operations
Line 4: Directory management
Line 5: System monitoring
EOF

# View entire file
cat sample.txt

# View with pagination
less sample.txt

# View first lines
head sample.txt
head -n 3 sample.txt

# View last lines
tail sample.txt
tail -n 2 sample.txt

# Count lines, words, characters
wc sample.txt
```

**Output:**
```
Line 1: Introduction to Linux
Line 2: Basic commands
Line 3: File operations
Line 4: Directory management
Line 5: System monitoring
```

---

## Session 6: Text Editing

```bash
# Edit with nano
nano myfile.txt
# [Add some content, save with Ctrl+O, exit with Ctrl+X]

# Edit with vim
vim script.sh
# [Press 'i' to insert, type content, Esc, :wq to save and quit]

# Verify file content
cat myfile.txt
cat script.sh
```

**Output:**
```
[Content of your edited files]
```

---

## Session 7: File Permissions

```bash
# Create a test script
echo '#!/bin/bash' > test_script.sh
echo 'echo "Hello from script"' >> test_script.sh

# Check initial permissions
ls -l test_script.sh

# Try to execute (should fail)
./test_script.sh

# Add execute permission
chmod +x test_script.sh

# Check new permissions
ls -l test_script.sh

# Execute script
./test_script.sh

# Various permission examples
chmod 755 test_script.sh
ls -l test_script.sh

chmod 644 myfile.txt
ls -l myfile.txt

chmod u+w,g-w,o-r sample.txt
ls -l sample.txt

# Change ownership (requires sudo)
sudo chown $USER:$USER myfile.txt
ls -l myfile.txt
```

**Output:**
```
Before: -rw-r--r-- 1 user user 45 Jan 31 10:30 test_script.sh
After:  -rwxr-xr-x 1 user user 45 Jan 31 10:30 test_script.sh

Hello from script
```

---

## Session 8: System Monitoring

```bash
# Process monitoring
top
# [Press 'q' to quit after observing]

# Install and use htop
sudo apt update
sudo apt install htop -y
htop
# [Press F10 to quit]

# Disk usage
df -h
du -sh ~/
du -h --max-depth=1 ~/

# Memory usage
free -m
free -h

# System information
uname -a
lscpu
uptime

# Check running processes
ps aux
ps aux | grep bash

# Network information
ifconfig  # or ip addr
ping -c 4 google.com
```

**Output:**
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1       100G   45G   50G  48% /

              total        used        free
Mem:           8G          3G          5G
Swap:          2G          0B          2G
```

---

## Session 9: Additional Useful Commands

```bash
# Find files
find ~ -name "*.txt"
find /home -type f -name "sample*"

# Search within files
grep "Linux" sample.txt
grep -r "error" /var/log/

# Command history
history
history | grep mkdir

# Clear screen
clear

# Get help
man ls
ls --help
which ls
```

**Output:**
```
[Paste your search and find outputs]
```

---

## Session 10: Project Setup for GitHub

```bash
# Create project structure
mkdir -p ~/linux-task/screenshots
mkdir -p ~/linux-task/docs

# Navigate to project
cd ~/linux-task

# Copy screenshots from Windows
cp /mnt/c/Users/msdsr/Pictures/"Devops T-1 SS"/*.png screenshots/

# Verify
ls -l screenshots/

# Initialize git
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git init

# Check status
git status
```

**Output:**
```
[Paste your git setup outputs]
```

---

## Commands Summary Statistics

```bash
# Count total commands used
history | wc -l

# Most used commands
history | awk '{print $2}' | sort | uniq -c | sort -rn | head -10
```

**Output:**
```
Total commands: [number]

Most used:
  45 ls
  32 cd
  23 mkdir
  18 cat
  15 chmod
  ...
```

---

## Notes and Observations

- **Key Learning:** [Add your observations]
- **Challenges Faced:** [Any difficulties encountered]
- **Solutions Found:** [How you solved problems]
- **Best Practices Learned:** [Important takeaways]

---

## Completion Checklist

- [x] Installed Ubuntu/WSL
- [x] Explored directory structure
- [x] Created and managed files/directories
- [x] Practiced file viewing and editing
- [x] Understood and modified permissions
- [x] Monitored system resources
- [x] Documented all commands
- [x] Captured screenshots
- [x] Prepared for GitHub upload

---

**End of Command Log**
