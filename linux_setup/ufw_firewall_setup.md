┌──(kali㉿kali)-[~]
└─$ sudo apt install ufw                                              
[sudo] password for kali: 
Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is held by process 5110 (apt)       
Reading package lists... 0%                                                   ufw is already the newest version (0.36.2-9).
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 4
                                                                              
┌──(kali㉿kali)-[~]
└─$ systemctl status ufw        
● ufw.service - Uncomplicated firewall
     Loaded: loaded (/usr/lib/systemd/system/ufw.service; enabled; preset: en>
     Active: active (exited) since Sat 2026-07-11 00:18:33 IST; 5h 18min left
 Invocation: 925fd99553fd4cd3924aad8bfc117778
       Docs: man:ufw(8)
   Main PID: 562 (code=exited, status=0/SUCCESS)
   Mem peak: 5M
        CPU: 39ms

Jul 11 00:18:33 kali systemd[1]: Starting ufw.service - Uncomplicated firewal>
Jul 11 00:18:33 kali systemd[1]: Finished ufw.service - Uncomplicated firewal>

                                                                              
┌──(kali㉿kali)-[~]
└─$ ufw default allow outgoing       
ERROR: You need to be root to run this script
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo ufw default allow outgoing
Default outgoing policy changed to 'allow'
(be sure to update your rules accordingly)
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo ufw default deny incoming
Default incoming policy changed to 'deny'
(be sure to update your rules accordingly)
                                                                              
┌──(kali㉿kali)-[~]
└─$ ifconfig               
eth0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
        ether 7c:8a:e1:91:12:ee  txqueuelen 1000  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 24  bytes 1280 (1.2 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 24  bytes 1280 (1.2 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

wlan0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.68.10.59  netmask 255.255.255.0  broadcast 10.68.10.255
        inet6 fe80::ed5c:d999:7337:ab7a  prefixlen 64  scopeid 0x20<link>
        inet6 2409:40d6:100e:9bc1:c7dc:f26:829e:f7bd  prefixlen 64  scopeid 0x0<global>
        inet6 2409:40d6:100e:9bc1:3d17:e0cc:2fc4:9f5d  prefixlen 64  scopeid 0x0<global>
        ether b0:60:88:dc:cc:fb  txqueuelen 1000  (Ethernet)
        RX packets 292901  bytes 385022558 (367.1 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 65554  bytes 12160530 (11.5 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

                                                                              
┌──(kali㉿kali)-[~]
└─$ 
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
Default incoming policy changed to 'deny'
(be sure to update your rules accordingly)
Default outgoing policy changed to 'allow'
(be sure to update your rules accordingly)
Firewall is active and enabled on system startup
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo ufw status verbose
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To                         Action      From
--                         ------      ----
67/udp on wlan0            ALLOW IN    Anywhere                  
53/udp on wlan0            ALLOW IN    Anywhere                  
67/udp (v6) on wlan0       ALLOW IN    Anywhere (v6)             
53/udp (v6) on wlan0       ALLOW IN    Anywhere (v6)             

Anywhere on eth0           ALLOW FWD   Anywhere on wlan0         
Anywhere (v6) on eth0      ALLOW FWD   Anywhere (v6) on wlan0    

                                                                              
┌──(kali㉿kali)-[~]
└─$     sudo ufw status numbered              
Status: active

     To                         Action      From
     --                         ------      ----
[ 1] 67/udp on wlan0            ALLOW IN    Anywhere                  
[ 2] 53/udp on wlan0            ALLOW IN    Anywhere                  
[ 3] Anywhere on eth0           ALLOW FWD   Anywhere on wlan0         
[ 4] 67/udp (v6) on wlan0       ALLOW IN    Anywhere (v6)             
[ 5] 53/udp (v6) on wlan0       ALLOW IN    Anywhere (v6)             
[ 6] Anywhere (v6) on eth0      ALLOW FWD   Anywhere (v6) on wlan0    

                                                                              
┌──(kali㉿kali)-[~]
└─$ 
