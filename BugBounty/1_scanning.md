# 1__
1st we just run am Nmap scan
> Nmap -A -F T2 ip -V
T2 is slowing the scanning which is required to be undetected 

# 2__
directory scanning
ffuf -w /usr/share/wordlists/dirb/common.txt -u http://tengt.htb/FUZZ -p 1

# 3__
seclists Download 
git clone https://github.com/danielmiessler/SecLists.git

# 4__
https://www.shodan.io/
> shodan
for API Key 
shodan < dashboard  < account API
> shodan init <api>

> shodan scan -h
Usage: shodan scan [OPTIONS] COMMAND [ARGS]...
Scan an IP/ netblock using Shodan.
Options:
-h, --help Show this message and exit.
Commands:
internet Scan the Internet for a specific port and protocol using the... list Show recently launched scans
protocols List the protocols that you can scan with using Shodan.
status Check the status of an on-demand scan.
submit
Scan an IP/ netblock using 

-(parallels®kali-linux-2022-2)-[~]
> shodan count wordpres

(parallels© kali-linux-2022-2)-[~]
> shodan count wordpress 
555377

parallels kali-linux-2022-2)-[~]
> shodan download wordpressfile "wordpress 1.4.7"

(parallels® kali-linux-2022-2)-[~]
> shodan count wordpress 1.4.7

(parallelskali-linux-2022-2)-[~]
> shodan download wordpressfile "wordpress 1.4.7"
Notice: fewer results were saved than requested
Saved 5 results into file wordpressfile.json.gz

-(parallels kali-linux-2022-2)-[~]
> gunzip wordpressfile.json.gz

-(parallels kali-linux-2022-2)-[~]
$ sudo apt install gedit
[sudo] password for parallels:
Reading package lists... Done
Building dependency tree... Done

parallels@kali-linux-2022-2)-[]
$ gedit wordpressfile.json

—(parallels© kali-linux-2022(~]
$ host yahoo.com

-(parallels kali-linux-2022-2)-[~]
$ ping yahoo.com

parallels®kali-linux-2022-2)-[~]
$ shodan host 98.137.11.163
80/tcp
443/tcp
SSL Versions: -SSLV2, -SSLV3, TLSV1, TLSv1.1, TLSV1.2, TLSV1.3

(parallelskali-linux-2022-2)-[~]
-$ shodan scan -h
Usage: shodan scan [OPTIONS] COMMAND [ARGS]

https://sub.domain.com/blog/artical/search?id=42

(kalikali)-[~/Desktop/sql] 
-$ dig axfr @10.10.10.123 friendzone.red
<<>> DiG 9.18.0-2-Debian <<>> axfr @10.10.10.123 friendzone.red



