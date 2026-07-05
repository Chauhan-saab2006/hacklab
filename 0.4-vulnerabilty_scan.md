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


