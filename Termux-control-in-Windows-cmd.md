🔐 Best Way: SSH from Windows → Termux
✅ Step 1: Prepare Termux (Phone)
In Termux:

pkg update && pkg upgrade
pkg install openssh
passwd
sshd
Now check your IP:

ip a
Look for something like:

192.168.x.x
Also confirm port:

Termux SSH runs on 8022

💻 Step 2: Connect from Windows
✔️ Option A: Built-in Windows SSH (Easiest)
Modern Windows already has SSH.

Open Command Prompt or PowerShell and run:

ssh u0_aXXX@192.168.x.x -p 8022
👉 Replace:

u0_aXXX → your actual Termux username (type whoami in Termux to confirm)

192.168.x.x → your phone IP
