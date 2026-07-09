┌──(kali㉿kali)-[~]
└─$ ^[[200~sudo apt update
zsh: bad pattern: ^[[200~sudo
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo apt install git -y~
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo apt update
sudo apt install git -y
[sudo] password for kali: 
Get:1 https://brave-browser-apt-release.s3.brave.com stable InRelease [7,547 B]
Get:2 https://brave-browser-apt-release.s3.brave.com stable/main amd64 Packages [30.1 kB]
Get:3 https://brave-browser-apt-release.s3.brave.com stable/main arm64 Packages [29.9 kB]
Get:4 https://kali.download/kali kali-rolling InRelease [34.0 kB]            
Get:5 https://kali.download/kali kali-rolling/main amd64 Packages [20.9 MB]  
Hit:6 https://us-central1-apt.pkg.dev/projects/antigravity-auto-updater-dev antigravity-debian InRelease
Get:7 https://kali.download/kali kali-rolling/main amd64 Contents (deb) [53.0 MB]
Get:8 https://kali.download/kali kali-rolling/contrib amd64 Packages [120 kB]                                                                                                                                                  
Get:9 https://kali.download/kali kali-rolling/contrib amd64 Contents (deb) [278 kB]                                                                                                                                            
Get:10 https://kali.download/kali kali-rolling/non-free amd64 Packages [188 kB]                                                                                                                                                
Get:11 https://kali.download/kali kali-rolling/non-free amd64 Contents (deb) [910 kB]                                                                                                                                          
Fetched 75.5 MB in 23s (3,312 kB/s)                                                                                                                                                                                            
186 packages can be upgraded. Run 'apt list --upgradable' to see them.
=git is already the newest version (1:2.53.0-1).
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 186
                                                                                                                                                                                                                                
┌──(kali㉿kali)-[~]
└─$ git config --global user.name "Chauhan-saab2006"
git config --global user.email "ac6845578@gmail.com"
                                                                                                                                                                                                                                
┌──(kali㉿kali)-[~]
└─$ ssh-keygen -t ed25519 -C "ac6845578@gmail.com"   
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/kali/.ssh/id_ed25519): /run/media/kali/New Volume/New Empty File
/run/media/kali/New Volume/New Empty File already exists.
Overwrite (y/n)? Y
Enter passphrase for "/run/media/kali/New Volume/New Empty File" (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /run/media/kali/New Volume/New Empty File
Your public key has been saved in /run/media/kali/New Volume/New Empty File.pub
The key fingerprint is:
SHA256:BcJOkf4yALg95lp6T0zLXehlrSgrJtNVWKb37uNDM08 ac6845578@gmail.com
The key's randomart image is:
+--[ED25519 256]--+
| .   .oo.        |
|. .   *. .       |
| o . O    .      |
|. + + =. o       |
| o ..+.oS .      |
|  o+.+o=*.E      |
| = .* +=.=       |
|= =. o  + .      |
| = oo  ooo       |
+----[SHA256]-----+
                                                                                                                                                                                                                                
┌──(kali㉿kali)-[~]
└─$ 
