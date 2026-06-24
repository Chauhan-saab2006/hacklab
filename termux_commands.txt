            termux app

" some commands of termux "
 
ifconfig                      = is used to know the ip address
nmap 'ip address ' -v         = to know the ports with details
nmap ' ip address ' -v -sn    = to know how many host are online
xxx.xxx.1.1                   = router ip adress
ctrl + c                      = is used for stoping the process
nmap "host ip address" -v     = to know which ports are open in this ip


1️⃣ Update & Upgrade Packages
pkg update
What it does:
Updates the list of available packages from repositories.

pkg upgrade
What it does:
Upgrades all installed packages to the latest version.

Storage Access
2️⃣ Setup Storage
termux-setup-storage
What it does:
Gives Termux permission to access your phone storage (Internal Storage, Downloads, etc.).

After running it you will see folders like:

~/storage/downloads

~/storage/shared

~/storage/dcim

File Management
3️⃣ List Files
ls
What it does:
Shows files and folders in the current directory.

4️⃣ Change Directory
cd foldername
What it does:
Moves into another folder.

Example:

cd storage
Go back:

cd ..
5️⃣ Create Folder
mkdir foldername
What it does:
Creates a new directory.

Example:

mkdir tools
6️⃣ Remove File
rm filename
Deletes a file.

Example:

rm test.txt
7️⃣ Remove Folder
rm -rf foldername
Deletes a folder and everything inside it.

Example:

rm -rf tools
Package Installation
8️⃣ Install Package
pkg install packagename
Example:

pkg install git
What it does:
Installs software packages.

9️⃣ Search Package
pkg search name
Example:

pkg search python
What it does:
Searches available packages.

Useful Commands
🔟 Clear Terminal
clear
What it does:
Clears the screen.

1️⃣1️⃣ Check Current Folder
pwd
What it does:
Shows your current directory path.

1️⃣2️⃣ Copy File
cp file1 file2
Example:

cp test.txt backup.txt
What it does:
Copies files.

1️⃣3️⃣ Move / Rename File
mv oldname newname
Example:

mv test.txt newtest.txt
What it does:
Moves or renames files.

Network Tools
Install Python
pkg install python
Install Git
pkg install git
Install Curl
pkg install curl
Pro Tip (Very Important)
Always run this first after installing Termux:

pkg update && pkg upgrade
This keeps your environment stable.

