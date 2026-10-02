# it will show if host is up or not
> namp -sn <taregr ip>


# to check how many devices are connected to local network
# it will take lot of time
> sudo netdiscover -i wlan0/eth0
> namp -sn 192.168.252.0/24

 Currently scanning: 172.26.0.0/16   |   Screen View: Unique Hosts                     
                                                                                       
 14 Captured ARP Req/Rep packets, from 1 hosts.   Total size: 588                      
 _____________________________________________________________________________
   IP            At MAC Address     Count     Len  MAC Vendor / Hostname      
 -----------------------------------------------------------------------------
 192.168.252.146 6a:af:2c:74:08:e0     14     588  Unknown vendor 

# it will scan from 1 to 200 addresses
> nmap -sn 192.168.252.1-200
Starting Nmap 7.991 ( https://nmap.org ) at 2026-09-20 10:56 +0530
Nmap scan report for cachyos.local (192.168.252.59)
Host is up (0.000033s latency).
Nmap scan report for Android.local (192.168.252.146)
Host is up (0.10s latency).
Nmap done: 200 IP addresses (2 hosts up) scanned in 11.03 seconds
[apma@cachyos hacklab]$ 

# if we have a list of ip's we want to scan if they are up or not 
> nmap -sn -iL /home/kali/Desktop/ip's.txt
# and also if we want to exclude the ip from scan 
> nmap -sn -iL 192.168.252.1-255 --excludefile /home/kali/Desktop/ips.txt

# if want to scan only few ip's we can use 
# -sn is for to check is host is up or not
# -Pn is for to scan port's on both ip's
> nmap -sn 192.168.252.1 192.168.252.122 
> nmap -Pn 192.168.252.1 192.168.252.122

