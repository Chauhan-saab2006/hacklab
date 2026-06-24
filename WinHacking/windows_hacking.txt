# to know the ip 
┌──(apma㉿kali)-[~]
└─$ ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:42:2c:25 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute eth0
       valid_lft 85368sec preferred_lft 85368sec
    inet6 fd17:625c:f037:2:b32:340c:fdf8:2a3d/64 scope global temporary dynamic 
       valid_lft 86057sec preferred_lft 14057sec
    inet6 fd17:625c:f037:2:a00:27ff:fe42:2c25/64 scope global dynamic mngtmpaddr noprefixroute 
       valid_lft 86057sec preferred_lft 14057sec
    inet6 fe80::a00:27ff:fe42:2c25/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
                                                                                   
 # .* is for all ports                                                                  
┌──(apma㉿kali)-[~]
└─$ sudo nmap -sn 10.0.2.15.* 
[sudo] password for apma: 
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-17 20:24 +0530
Failed to resolve "10.0.2.15.*".
WARNING: No targets were specified, so 0 hosts scanned.
Nmap done: 0 IP addresses (0 hosts up) scanned in 0.60 seconds
                                                                                      
┌──(apma㉿kali)-[~]
└─$ sudo nmap -sn 10.0.2.255.*
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-17 20:25 +0530
Failed to resolve "10.0.2.255.*".
WARNING: No targets were specified, so 0 hosts scanned.
Nmap done: 0 IP addresses (0 hosts up) scanned in 0.50 seconds
                                                                                      
┌──(apma㉿kali)-[~]
└─$ sudo nmap -sn 10.0.2.*    
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-17 20:25 +0530
Nmap scan report for 10.0.2.2
Host is up (0.00058s latency).
MAC Address: 52:55:0A:00:02:02 (Unknown)
Nmap scan report for 10.0.2.3
Host is up (0.0011s latency).
MAC Address: 52:55:0A:00:02:03 (Unknown)
Nmap scan report for 10.0.2.15
Host is up.
Nmap done: 256 IP addresses (3 hosts up) scanned in 3.19 seconds
# ping is to know ttl & and packets which help to identify the os                                                                                      
┌──(apma㉿kali)-[~]
└─$ ping 10.0.2.2
PING 10.0.2.2 (10.0.2.2) 56(84) bytes of data.
64 bytes from 10.0.2.2: icmp_seq=1 ttl=255 time=3.92 ms
64 bytes from 10.0.2.2: icmp_seq=2 ttl=255 time=0.456 ms
64 bytes from 10.0.2.2: icmp_seq=3 ttl=255 time=0.540 ms
64 bytes from 10.0.2.2: icmp_seq=4 ttl=255 time=0.592 ms
64 bytes from 10.0.2.2: icmp_seq=5 ttl=255 time=0.718 ms
64 bytes from 10.0.2.2: icmp_seq=6 ttl=255 time=0.492 ms
64 bytes from 10.0.2.2: icmp_seq=7 ttl=255 time=1.35 ms
64 bytes from 10.0.2.2: icmp_seq=8 ttl=255 time=1.80 ms
64 bytes from 10.0.2.2: icmp_seq=9 ttl=255 time=1.64 ms
64 bytes from 10.0.2.2: icmp_seq=10 ttl=255 time=0.492 ms


^C
--- 10.0.2.2 ping statistics ---
35 packets transmitted, 35 received, 0% packet loss, time 35327ms
rtt min/avg/max/mdev = 0.433/1.110/3.919/0.836 ms

# -O is for os detection
                                                                                      
┌──(apma㉿kali)-[~]
└─$ sudo nmap -O 10.0.2.2           
[sudo] password for apma: 
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-17 20:48 +0530
Nmap scan report for 10.0.2.2
Host is up (0.0013s latency).
Not shown: 996 filtered tcp ports (no-response)
PORT     STATE SERVICE
135/tcp  open  msrpc
445/tcp  open  microsoft-ds
3389/tcp open  ms-wbt-server
7070/tcp open  realserver
MAC Address: 52:55:0A:00:02:02 (Unknown)
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Aggressive OS guesses: AT&T BGW210 voice gateway (93%), Oracle Virtualbox Slirp NAT bridge (90%), QEMU user mode network gateway (88%), HP 9100c Digital Sender printer (J3113A) (86%), Minolta Di550 laser printer (85%), NEC SuperScript printer (85%), Cisco SG 500 switch (85%), Yamaha RX-V2067 or RX-V3900 audio receiver (85%)
No exact OS matches for host (test conditions non-ideal).
Network Distance: 1 hop

OS detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 10.40 seconds

# -p is for specific ports for scanning 
                                                                                      
┌──(apma㉿kali)-[~]
└─$ nmap -p 22 10.15.212.23
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-19 16:17 +0530
Nmap scan report for 10.15.212.23
Host is up (0.00077s latency).

PORT   STATE    SERVICE
22/tcp filtered ssh

Nmap done: 1 IP address (1 host up) scanned in 0.80 seconds
                                                                                   
┌──(apma㉿kali)-[~]
└─$ nmap -p 7-593 10.15.212.23
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-19 16:18 +0530
Nmap scan report for 10.15.212.23
Host is up (0.0017s latency).
Not shown: 583 filtered tcp ports (no-response)
PORT    STATE  SERVICE
135/tcp open   msrpc
137/tcp closed netbios-ns
139/tcp open   netbios-ssn
445/tcp open   microsoft-ds

Nmap done: 1 IP address (1 host up) scanned in 4.20 seconds


┌──(apma㉿kali)-[~]
└─$ sudo nmap -O 10.15.212.23
[sudo] password for apma: 
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-19 16:40 +0530
Nmap scan report for 10.15.212.23
Host is up (0.0012s latency).
Not shown: 998 filtered tcp ports (no-response)
PORT     STATE SERVICE
3389/tcp open  ms-wbt-server
7070/tcp open  realserver
MAC Address: 52:E2:D2:85:14:78 (Unknown)
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Device type: general purpose
Running: Microsoft Windows 10|11
OS CPE: cpe:/o:microsoft:windows_10 cpe:/o:microsoft:windows_11
OS details: Microsoft Windows 10 - 11
Network Distance: 1 hop

OS detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 11.31 seconds

# -sA is for to check is firewall enabled or not if it show filtered it mean yes if unfiltered it mean no

┌──(apma㉿kali)-[~]
└─$ nmap -sA 10.15.212.49    
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-19 16:44 +0530
Nmap scan report for 10.15.212.49
Host is up (0.00093s latency).
All 1000 scanned ports on 10.15.212.49 are in ignored states.
Not shown: 1000 unfiltered tcp ports (reset)
MAC Address: 08:00:27:6B:40:57 (Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 2.86 seconds

# -f for fragments of packets -sV for service version
       
┌──(apma㉿kali)-[~]
└─$ sudo nmap -f -sV 10.15.212.49
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-19 16:47 +0530
Nmap scan report for 10.15.212.49
Host is up (0.00049s latency).
All 1000 scanned ports on 10.15.212.49 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)
MAC Address: 08:00:27:6B:40:57 (Oracle VirtualBox virtual NIC)

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 28.26 seconds
                                                                 
# -sS is for SYN scan and

┌──(apma㉿kali)-[~/hack]
└─$ sudo wireshark                  
[sudo] password for apma: 
 ** (wireshark:27232) 17:00:19.612397 [Capture MESSAGE] -- Capture Start ...
 ** (wireshark:27232) 17:00:19.680313 [Capture MESSAGE] -- Capture started
 ** (wireshark:27232) 17:00:19.681712 [Capture MESSAGE] -- File: "/tmp/wireshark_eth0VBH1L3.pcapng"

# wireshark is for seeing packs movements
                                                                                   
┌──(apma㉿kali)-[~]
└─$ sudo nmap -sS -sV 10.15.212.49
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-19 17:00 +0530
Nmap scan report for 10.15.212.49
Host is up (0.011s latency).
All 1000 scanned ports on 10.15.212.49 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)
MAC Address: 08:00:27:6B:40:57 (Oracle VirtualBox virtual NIC)

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 24.03 seconds
                                                                                   
┌──(apma㉿kali)-[~]
└─$ 

# -D is for using multiple ip for scanning 
┌──(apma㉿kali)-[~]
└─$ sudo nmap -sS -D RND:5  10.15.212.49
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-19 17:11 +0530
Nmap scan report for 10.15.212.49
Host is up (0.0021s latency).
All 1000 scanned ports on 10.15.212.49 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)
MAC Address: 08:00:27:6B:40:57 (Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 24.04 seconds
                                                                                   
┌──(apma㉿kali)-[~]
└─$ 


# -D is also can sue for ip spoofing 10.15.212.82 is fack ip for scanning

 Currently scanning: 172.16.0.0/16   |   Screen View: Unique Hosts                          
                                                                                            
 9 Captured ARP Req/Rep packets, from 2 hosts.   Total size: 540                            
 _____________________________________________________________________________
   IP            At MAC Address     Count     Len  MAC Vendor / Hostname      
 -----------------------------------------------------------------------------
 10.15.212.82    16:81:53:d0:a3:a4      2     120  Unknown vendor                           
 10.15.212.49    08:00:27:6b:40:57      7     420  PCS Systemtechnik GmbH                   


 
┌──(apma㉿kali)-[~]
└─$ sudo nmap -sS -D 10.15.212.82 10.15.212.49
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-19 17:21 +0530
Nmap scan report for 10.15.212.49
Host is up (0.0014s latency).
All 1000 scanned ports on 10.15.212.49 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)
MAC Address: 08:00:27:6B:40:57 (Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 23.27 seconds
                                                                                             
┌──(apma㉿kali)-[~]
└─$ 

# -A is for all in one scanner which can do 3 "-sC , -O , -sV"different scan
┌──(apma㉿kali)-[~]
└─$ nmap -A 10.15.212.49 
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-19 17:26 +0530
Nmap scan report for 10.15.212.49
Host is up (0.0018s latency).
All 1000 scanned ports on 10.15.212.49 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)
MAC Address: 08:00:27:6B:40:57 (Oracle VirtualBox virtual NIC)
Too many fingerprints match this host to give specific OS details
Network Distance: 1 hop

TRACEROUTE
HOP RTT     ADDRESS
1   1.77 ms 10.15.212.49

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 35.27 seconds
                                                                                             
┌──(apma㉿kali)-[~]
└─$ 


