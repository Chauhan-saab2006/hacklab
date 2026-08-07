using nmap :





ports            protocol         service name                         USE  
20                TCP             FTP DATA TRANSFER              Transfer file in FTP sessions
21                TCP             FTP command control            command and control in FTP sessions
22                TCP                SSH                         secure remote login and command exception    
25                TCP                SMTP                        sending email b/w servers
53                UDP                DNS                         resolving domain name to ip addresses
80                TCP                HTTP                        tranmitting web pages over internet
443               TCP                HTTPS                       secure web traffic , encrypting data b/w the client and server



sudo nmao -sS -sV -sC scanme.nmap.org
                                      (-sS is for tcp sin scan)
                                      (-sV is for version scan)
                                      (-sC is for script scan)
                                      (-O is for os scan)

it take so much time 

alternative 

sudo nmap -A tanget domain name


and explore other things of nmap



VULNERABILTY SCANNING

EXTERNAL SCAN :
               DESCRIPTION: target externally-facing ip addresses to identify vulnerabilty in perameter and
               cloud system
               ACCESS LEVEL: public-facing
               purpose: access security posture from an external perspective

INTERNAL SCAN :
              DISCRIPTION: conduct within the organization's network to find vulnerabilty in internal system of application
              ACCESS LEVEL: internal network access
              PURPOSE: identify risks that could be exploited after a breach

UNATHENTICATED SCANS :
                      DISCRIPTION: perform scan without valid credentials, repling on publicly accessible information to find vulnerabilties
                      ACCESS LEVEL: no credentials required
                      PURPOSE: direct basic weaknesses visible to external attackers

ATHENTICATED SCAN :
                   DISCRIPTION: use valid credentials to access deeper layers of the system for a comprehensive vulnerabilty assessment
                   ACCESS LEVEL: valid user credentials 
                   PURPOSE: uncover hidden vulnerabilties and compliance issues
                    

DOWNLOAD NESSUSED ESSENTALS form tenable
 
1. ls
2. Downloads
3. ls
4. sudo dpkg -i Nessus-10.8.4-ubuntu1604_amd64.deb
5. sudo systemctl start nessusd.service 
6. sudo systemctl status nessusd.service

go to https:/kali:8834
and regester
and wait till complete compilation plugins

we can scan by using scan templates
1. add name
2. ip address
3. launch the scan 


