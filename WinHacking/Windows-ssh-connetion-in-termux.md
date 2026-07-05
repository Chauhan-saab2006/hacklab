🔐 Step 1: Enable SSH on Windows
Windows has a built-in OpenSSH server.

On your Windows laptop:
Open PowerShell as Administrator

Run:
> Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
Start SSH server:

> Start-Service sshd
Enable auto-start:

> Set-Service -Name sshd -StartupType Automatic
🔍 Step 2: Get your Windows IP
In Command Prompt:

> ipconfig
Look for:

IPv4 Address . . . . . . . . . . : 192.168.x.x
📱 Step 3: Connect from Termux
In Termux:
>ssh YOUR_WINDOWS_USERNAME@192.168.x.x
Example:

> ssh lenovo@192.168.1.10
⚠️ First-time connection
You’ll see:

Are you sure you want to continue connecting?
Type:
yes
Then enter your Windows password.

✅ Done
Now your Termux controls your Windows terminal via SSH.
