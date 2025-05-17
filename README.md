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
