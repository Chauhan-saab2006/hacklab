## 📂 1. File & Directory Management

```bash
pwd              # Show current directory
ls               # List files
ls -la           # Detailed list (including hidden files)
cd /path         # Change directory
cd ..            # Move one level up
mkdir folder     # Create directory
rmdir folder     # Remove empty directory
rm file.txt      # Delete file
rm -rf folder    # Delete directory recursively (⚠️ dangerous)
cp file1 file2   # Copy file
mv file1 file2   # Move or rename file
```

---

## 📄 2. File Viewing & Editing

```bash
cat file.txt         # Display file contents
less file.txt        # View file with scrolling
head file.txt        # First 10 lines
tail file.txt        # Last 10 lines
tail -f log.txt      # Monitor logs live
nano file.txt        # Simple text editor
vim file.txt         # Advanced editor
```

---

## 🔍 3. Searching & Filtering

```bash
find / -name file.txt        # Search for file
grep "text" file.txt         # Search inside file
grep -r "text" /dir          # Recursive search
locate file.txt              # Fast file search
which python                 # Locate binary
```

---

## ⚙️ 4. System Information

```bash
whoami        # Current user
id            # User details
uname -a      # System info
top           # Running processes
htop          # Interactive process viewer
df -h         # Disk usage
free -h       # Memory usage
uptime        # System uptime
```

---

## 🔐 5. Permissions & Ownership

```bash
chmod 755 file.sh     # Change permissions
chmod +x script.sh    # Make executable
chown user:user file  # Change ownership
```

---

## 🌐 6. Networking Commands

```bash
ifconfig            # Show network interfaces (old)
ip a                # Show IP addresses
ping google.com     # Test connectivity
netstat -tulnp      # Open ports and services
ss -tulnp           # Modern alternative
curl example.com    # Fetch web content
wget url            # Download files
```

---

## 📦 7. Package Management (APT)

```bash
apt update          # Update package list
apt upgrade         # Upgrade system packages
apt install tool    # Install package
apt remove tool     # Remove package
```

---

## 👤 8. User Management

```bash
adduser username    # Create user
passwd username     # Set password
su username         # Switch user
sudo command        # Run as root
```

---

## 🔄 9. Process Management

```bash
ps aux              # List processes
kill PID            # Stop process
kill -9 PID         # Force kill
bg                  # Run in background
fg                  # Bring to foreground
```

---

## 📦 10. Compression & Archiving

```bash
tar -cvf file.tar folder    # Create archive
tar -xvf file.tar           # Extract archive
zip file.zip file.txt       # Compress file
unzip file.zip              # Extract zip
```

---

## ⌨️ 11. Terminal Shortcuts

```bash
Tab            # Auto-complete
Ctrl + C       # Stop process
Ctrl + Z       # Pause process
Ctrl + L       # Clear terminal
history        # Show command history
```

---

## 🧪 12. Basic Kali Linux Security Tools

```bash
nmap -sV target        # Scan ports and services
hydra -l user -P pass.txt ssh://IP
msfconsole             # Metasploit framework
aircrack-ng            # Wireless security testing
nikto -h target        # Web vulnerability scanner
```

---

## ⚠️ Important Notes

* Always double-check commands like `rm -rf`
* Use `sudo` carefully
* Practice in a lab environment, not on unauthorized 


# 🐉 Kali Linux Advanced Commands & Cybersecurity Usage Guide

---

## 🧠 13. Advanced File Operations

```bash id="u7y2df"
stat file.txt            # Detailed file information
file file.txt            # Identify file type
du -sh *                 # Show folder sizes
tree                     # Display directory structure
ln -s target link        # Create symbolic link
```

📌 Use Case: Detect suspicious or hidden files during investigations.

---

## 🔥 14. Advanced Text Processing

```bash id="q2kcw9"
cut -d ":" -f1 /etc/passwd     # Extract specific columns
awk '{print $1}' file.txt      # Print specific column
sort file.txt                  # Sort content
uniq file.txt                  # Remove duplicates
wc -l file.txt                 # Count lines
tr 'a-z' 'A-Z'                 # Change case
```

📌 Use Case: Log parsing, extracting indicators of compromise (IOCs).

---

## 🧬 15. Pipes & Redirection

```bash id="q0ff6n"
cat file.txt | grep "error"
ls -la | less
echo "hello" > file.txt
echo "world" >> file.txt
command1 | command2
```

📌 Use Case: Chain commands for powerful workflows.

---

## 📡 16. Advanced Networking

```bash id="d0p8ot"
arp -a                 # View ARP table
route                  # Routing table
traceroute google.com  # Trace network path
dig google.com         # DNS lookup
nslookup google.com    # DNS query
nc -lvnp 4444          # Netcat listener
nc target 4444         # Connect to port
```

📌 Use Case: Network reconnaissance and troubleshooting.

---

## 🕵️ 17. Log Analysis

```bash id="24o8o1"
cat /var/log/syslog
grep "failed" /var/log/auth.log
last                  # Login history
lastb                 # Failed login attempts
journalctl            # System logs
```

📌 Use Case: Detect brute-force attacks or suspicious activity.

---

## ⚔️ 18. Privilege Escalation Enumeration

```bash id="0v5qfw"
sudo -l                # Check sudo permissions
id                     # User privileges
uname -r               # Kernel version
ps aux | grep root     # Root processes
```

📌 Use Case: Identify misconfigurations during penetration testing.

---

## 🧪 19. Bash Scripting Basics

```bash id="h9nt6k"
#!/bin/bash
echo "Hello Hacker"
```

Run script:

```bash id="gq8q8p"
chmod +x script.sh
./script.sh
```

📌 Use Case: Automate repetitive security tasks.

---

## 🔐 20. Password & Hash Tools

```bash id="9e9u4m"
john hash.txt
hashcat -m 0 hash.txt wordlist.txt
```

📌 Use Case: Password auditing and cracking exercises.

---

## 🌍 21. Web Testing Commands

```bash id="gxz3ko"
whatweb target.com
gobuster dir -u target.com -w wordlist.txt
curl -I target.com
```

📌 Use Case: Discover hidden directories and analyze web targets.

---

## 📦 22. Service Management

```bash id="ql1s4q"
systemctl start apache2
systemctl stop apache2
systemctl status apache2
service ssh start
```

📌 Use Case: Manage services during testing or lab setup.

---

## 🧠 23. Environment Variables

```bash id="g37kbi"
env
echo $PATH
export NAME="kali"
```

📌 Use Case: Useful in scripting and exploitation.

---

## ⚡ 24. Cron Jobs

```bash id="x9v1km"
crontab -l
crontab -e
```

📌 Use Case: Task automation or persistence mechanisms.

---

## 🧩 25. Disk & Mounting

```bash id="3u8q3y"
mount
umount /dev/sdb1
lsblk
fdisk -l
```

📌 Use Case: Analyze storage devices during forensic investigations.

---

## 🧠 Key Concept: Command Chaining

cat auth.log | grep "failed" | wc -l