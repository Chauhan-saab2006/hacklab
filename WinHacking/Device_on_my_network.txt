# check what is my ip
(kim®kali)-[~]
> ip a

File System Trash 1: lo: <LOOPBACK, UP, LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group defau lt qlen 1000
link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
inet 127.0.0.1/8 scope host lo
alid_lft forever:: 1/128 scope preferred lft forever Host noprefixroute
valid_lft forever preferred_lft forever
eth0: <BROADCAST, MULTICAST, UP, LOWER_UP> mtu 1500 qdisc Tq_couet state UP 2:up default qlen 1000
link/ether 52:54:00:2b:92:50 brd ff:ff:ff:ff:ff:ff
inet e eth0 192.168.122.71/24 brd 192.168.122.255 scope global dynamic gronoprefixrou
valid_lft 2951sec preferred_lft 2951sec
inet6 fe80:: 41d5:f9f:97a4:8c22/64 scope link valid_lft forever preferred_lft forever

# grep only ip on my network 
(kim®kali)-[~]
> sudo nmap 192.168.122.0/24  -sn -n -oA tnet | grep for | cut -d" " -f5
-sn. # for disable port scanning
-n.  # disable dns resolution
-oA tnet # Saves the results in all formats, prefixed tnet. (i.e. tnet.gnmap, tnet.nmap, and tnet.xml)
grep for # keeps only the lines containing the word "for".(i.e. line starting with "nmap scan report for...")
cut -d" " -f5 # takes each of those lines and pulls out the fifth space-separated field (which is the IP address itself

192.168.122.1
192.168.122.35
192.168.122.40
192.168.122.139
192.168.122.192
192.168.122.240
192.168.122.71


-(kim®kali)-[~]
-S cat tnet.nmap
Nmap 7.95 scan initiated Sat May 30 14:49:18 2026 |
-sn -n -oA tnet 192.168.122.0/24
Nmap scan report for 192.168.122.1
Host is up (0.00043s latency).
MAC Address: 52:54:00:63:AB:BE (QEMU virtual NIC) Nmap scan report for 192.168.122.35
Host is up (0.00080s latency).
MAC Address: 52:54:00:B7:90:F1 (QEMU
Nmap scan report for 192.168.122.40
Host is up (0.00085s latency).


(kim®kali)-[~]
-$ cd Downloads &&
hosts.lst

(kim® kali)-[~/Downloads]
cat hosts.lst

192.168.122.1
192.168.122.35
192.168.122.40
192.168.122.139.       developer workstations
192.168.122.192
192.168.122.240.      printer
192.168.122.71.        


-(kim® kali)-[~/Downloads]
> sudo nmap -sn -n -oA tnet -iL hosts.lst | grep for | cut -d" " -f5

-iL hosts.lst  # instead of 192.168.122.0/24 as previously

[sudo] password for kim:
192.168.122.35
192.168.122.40
192.168.122.139

# scanning for some specific ips
-(kim®kali)-[~]
>  sudo nmap -sn -n -oA tnet 192.168.122.35 192.168.122.40 192.168.122.139 grep for | cut -d" " -f5
[sudo] password for kim:
192.168.122.35
192.168.122.40
192.168.122.139

kim@kali: kim@kali:
>  sudo nmap 192.168.122.35 -sn -oA host 
[sudo] password for kim
Starting Nmap 7.95 ( https://nmap.org ) at 2026-05-30 09:37
Nmap scan report for vm (192.168.122.35)
Host is up (0.00052s latency).
MAC Address: 52:54:00:B7:90:F1 (QEMU virtual NIC)
Nmap done: 1 IP address (1 host up) scanned in 0.09


-(kim®kali)-[~]
> sudo nmap 192.168.122.35 -sn -oA host -PE --packet-trace

-packet-trace # print every single packet you send and receive
-PE # use ICMP as the discovery method
Starting Nmap 7.95 ( https://nmap.org ) at 2026-05-30 09:43 EDT SENT (0.0337s) ARP who-has 192.168.122.35 tell 192.168.122.71 RCVD (0.0341s) ARP reply 192.168.122.35 is-at 52:54:00:B7:90:F1
NSOCK INFO [0.0690s] 68.122.1:53 (IOD #1) EID 8
NSOCK INFO [0.0690s] nsock_iod_new2(): nsock_iod_new (IOD #1)
NSOCK INFO [0.0690s] nsock_read(): Read request from IOD #1 [192.168.122.1: 53] (timeout: -1ms) EID 18
NSOCK INFO [0.0690s] nsock_write(): Write request for 45 bytes to IOD #1 D 27 [192.168.122.1:53]
NSOCK INFO [0.0690s] nsock_trace_handler_callback(): Callback: CONNECT SUCC ESS for EID 8 [192.168.122.1:53]
NSOCK INFO [0.0690s] nsock_trace_handler_callback(): Callback: WRITE SUCCES
Nmap scan report for vm (192.168.122.35)
Host is up (0.00047s latency).
MAC Address: 52:54:00:B7:90:F1 (QEMU virtual NIC)
Nmap done: 1 IP address (1 host up) scanned in 0.10 seconds


-(kim®kali)-[~]
> sudo nmap 192.168.122.35 -sn -oA host -PE --reason 
Starting Nmap 7.95 ( https://nmap.org ) at 2026-05-30 09:48 EDT 
Nmap scan report for vm (192.168.122.35) 
Host is up, received arp-response (0.00062s latency).
MAC Address: 52:54:00:B7:90:F1 (QEMU virtual NIC) 
Nmap done: 1 IP address (1 host up) scanned in 0.08 seconds

-(kim®kali)-[~]
> sudo nmap 192.168.122.35 -sn -oA host -PE --packet-trace --disable-arp- ping
Starting Nmap 7.95 ( https://nmap.org ) at 2026-05-30 09:55 EDT
|SENT (0.0226s) ICMP [192.168.122.71 > 192.168.122.35 Echo request (type=8/
ode=0) id=1904 seq=0] IP [ttl=54 id=54528 iplen=28 ]
RCVD (0.0230s) ICMP [192.168.122.35 > 192.168.122.71 Echo reply (type=0/cod e=0) id=1904 seq=0] IP [ttl=64 id=30678 iplen=28 ]
NSOCK INFO [0.0740s] nsock_iod_new2(): nsock_iod_new (IOD #1)
NSOCK INFO [0.0740s] nsock_connect_udp(): UDP connection requested to 192.1 68.122.1:53 (IOD #1) EID 8
NSOCK INFO [0.0740s] nsock_read(): Read request from IOD #1 [192.168.122.1: (timeout: -1ms) EID 18 53]
NSOCK INFO [0.0740s] nsock_write(): Write request for 45 bytes to IOD #1 EI D 27 [192.168.122.1:53]
