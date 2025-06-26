# 🐧 Linux Commands Cheatsheet (Basic to Advanced)

## 📁 File and Directory Operations

| Command | Description |
|--------|-------------|
| `ls` | List directory contents |
| `ls -la` | List all files with permissions |
| `cd /path` | Change directory |
| `pwd` | Print working directory |
| `mkdir dir` | Create a directory |
| `rm file` | Remove a file |
| `rm -r dir` | Remove a directory recursively |
| `touch file` | Create an empty file |
| `cp file1 file2` | Copy a file |
| `mv file1 file2` | Move/rename a file |

## 📄 Viewing and Editing Files

| Command | Description |
|--------|-------------|
| `cat file` | View file content |
| `less file` | View file (scrollable) |
| `head file` | First 10 lines of a file |
| `tail file` | Last 10 lines of a file |
| `tail -f file` | Follow a file (live log) |
| `nano file` | Edit file using Nano |
| `vi file` | Edit file using Vim |

## 🔍 Searching and Filtering

| Command | Description |
|--------|-------------|
| `grep 'text' file` | Search for text in file |
| `find / -name file.txt` | Find file by name |
| `locate file` | Find file using database |
| `which command` | Path of a command |
| `man ls` | Manual/help for a command |

## 🔐 Permissions and Ownership

| Command | Description |
|--------|-------------|
| `chmod 755 file` | Change file permissions |
| `chown user:group file` | Change ownership |
| `umask` | Default permission settings |

## 📦 Package Management

**Debian/Ubuntu:**

```bash
sudo apt update
sudo apt install <package>
sudo apt remove <package>
```

**Red Hat/CentOS:**

```bash
sudo yum install <package>
sudo dnf install <package>  # Newer RHEL
```

**Arch Linux:**

```bash
sudo pacman -S <package>
```

## 📊 System Monitoring

| Command | Description |
|--------|-------------|
| `top` | Dynamic process viewer |
| `htop` | Enhanced `top` (requires install) |
| `ps aux` | View running processes |
| `free -h` | Show memory usage |
| `df -h` | Show disk space |
| `du -sh *` | Disk usage per file/folder |
| `uptime` | System load and uptime |
| `vmstat` | Memory, CPU, I/O stats |

## 🌐 Networking

| Command | Description |
|--------|-------------|
| `ip a` | Show IP addresses |
| `ping host` | Ping a host |
| `curl URL` | Fetch a URL |
| `wget URL` | Download a file |
| `netstat -tulnp` | Show listening ports |
| `ss -tuln` | Show socket stats |
| `traceroute host` | Trace route to a host |
| `nslookup domain` | DNS lookup |
| `dig domain` | DNS information |

## 🔄 Process Management

| Command | Description |
|--------|-------------|
| `kill PID` | Kill process by PID |
| `killall name` | Kill process by name |
| `bg` / `fg` | Resume job in background/foreground |
| `jobs` | List background jobs |
| `nohup command &` | Run command immune to hangups |

## 📋 Disk and File System

| Command | Description |
|--------|-------------|
| `mount /dev/sdX /mnt` | Mount a disk |
| `umount /mnt` | Unmount a disk |
| `lsblk` | List block devices |
| `fdisk -l` | List partitions |
| `mkfs.ext4 /dev/sdX` | Format disk |
| `fsck /dev/sdX` | Check and repair file system |

## ⏲️ Scheduling Tasks

| Command | Description |
|--------|-------------|
| `crontab -e` | Edit user cron jobs |
| `crontab -l` | List user cron jobs |
| `at 10am` | Schedule one-time task |

**Example cron syntax:**

```bash
* * * * * /path/script.sh
# ┬ ┬ ┬ ┬ ┬
# │ │ │ │ │
# │ │ │ │ └─ Day of Week (0 - 7)
# │ │ │ └─── Month (1 - 12)
# │ │ └───── Day of Month (1 - 31)
# │ └─────── Hour (0 - 23)
# └───────── Minute (0 - 59)
```

## ⚙️ System Control

| Command | Description |
|--------|-------------|
| `reboot` | Restart system |
| `shutdown -h now` | Power off |
| `systemctl start service` | Start a service |
| `systemctl stop service` | Stop a service |
| `systemctl status service` | Status of service |
| `systemctl enable service` | Enable service on boot |
| `journalctl -xe` | View system logs |

## 💡 Advanced / Scripting

| Command | Description |
|--------|-------------|
| `bash script.sh` | Run a script |
| `source ~/.bashrc` | Reload config |
| `alias ll='ls -la'` | Create command alias |
| `export VAR=value` | Set environment variable |
| `xargs` | Build and execute commands from input |
| `awk`, `sed`, `cut` | Text processing tools |
| `` `command` `` or `$(command)` | Command substitution |




#########################


# 🐧 Linux & Git Command Reference

## 📁 Basic Git Setup

```bash
# Set global Git username and email
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Initialize a new Git repo
git init

# Add a remote origin
git remote add origin https://github.com/your/repo.git

# Add files and commit
git add .
git commit -m "Initial commit"

# Push to GitHub
git push -u origin main
```

## 🔑 SSH Key Generation

```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your_email@example.com"

# Add the SSH key to the ssh-agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Display public key to add in GitHub/other
cat ~/.ssh/id_ed25519.pub
```

## 👤 User & Group Management

```bash
# Create a new user
sudo adduser username

# Add existing user to a group
sudo usermod -aG groupname username

# Create a new group
sudo groupadd groupname

# Switch to another user
su - username

# Show groups for a user
groups username

# Delete user
sudo deluser username

# Delete group
sudo groupdel groupname
```

## 🗂️ File Permissions & Ownership

### Change Permissions

```bash
# Read (r), write (w), execute (x) using chmod

# Set permission using symbolic
chmod u+x script.sh  # Add execute to user
chmod g-w file.txt   # Remove write from group

# Set permission using numeric
chmod 755 file.sh    # rwxr-xr-x
```

### Ownership

```bash
# Change owner
sudo chown user:group filename

# Recursive ownership change
sudo chown -R user:group /path/
```

## 🔢 Permission Binary Table

| Symbol | Binary | Numeric |
|--------|--------|---------|
| ---    | 000    | 0       |
| --x    | 001    | 1       |
| -w-    | 010    | 2       |
| -wx    | 011    | 3       |
| r--    | 100    | 4       |
| r-x    | 101    | 5       |
| rw-    | 110    | 6       |
| rwx    | 111    | 7       |

> **Example:** `chmod 754 file.sh` → `rwxr-xr--`

## 💻 APT Package Management (Debian/Ubuntu)

```bash
# Update package list
sudo apt update

# Upgrade installed packages
sudo apt upgrade

# Install a new package
sudo apt install packagename

# Remove a package
sudo apt remove packagename

# Remove package + config files
sudo apt purge packagename

# Clean cache
sudo apt autoremove
sudo apt clean
```

## 🔍 File Search & Filters

### `grep` – Search in files

```bash
# Find text in file
grep "pattern" file.txt

# Recursive grep in directory
grep -r "pattern" /path/

# Case-insensitive search
grep -i "pattern" file.txt
```

### `awk` – Text processing

```bash
# Print 1st column from file
awk '{print $1}' file.txt

# Print lines with specific word
awk '/pattern/' file.txt
```

### `find` – Locate files by name/type

```bash
# Find file by name
find /path -name filename.txt

# Find directories
find . -type d -name "config"

# Find files modified in last 1 day
find . -mtime -1
```

## ⚙️ System Monitoring & Info

```bash
# Show running processes
top

# System info
uname -a

# Memory usage
free -h

# Disk usage
df -h
du -sh foldername/

# Network info
ip a
```

## 🧰 Miscellaneous

```bash
# List files with permissions
ls -l

# List all including hidden
ls -la

# Print current path
pwd

# Copy file
cp file1.txt file2.txt

# Move/rename file
mv file1.txt newname.txt

# Remove file/folder
rm file.txt
rm -r folder/
```

## 🌍 Network & Curl

```bash
# Ping a host
ping google.com

# Fetch URL
curl https://example.com

# Download file
wget https://example.com/file.zip
```

