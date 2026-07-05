┌──(root㉿kali)-[/home/kali]
└─# sudo apt update      
sudo apt install pipx

┌──(root㉿kali)-[/home/kali]
└─# git clone https://github.com/mvt-project/mvt.git
or 
┌──(root㉿kali)-[/home/kali]
└─#  pipx install mvt    

┌──(root㉿kali)-[/home/kali]
└─# cd mvt 

┌──(root㉿kali)-[/home/kali]
└─# pipx ensurepath   

┌──(root㉿kali)-[/home/kali]
└─# source ~/.bashrc 

┌──(root㉿kali)-[/home/kali]
└─# mvt-android check-adb

advance indicator:
┌──(root㉿kali)-[/home/kali/mvt]
└─# mvt-android download-iocs
