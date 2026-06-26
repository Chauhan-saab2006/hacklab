#
root@kali:-/week3# python -m SimpleHTTPServer 80 
Serving HTTP on 0.0.0.0 port 80

#
root@kali:-/week3# python3 -m http.server 80
Serving HTTP on 0.0.0.0 port 80 (http://0.0.0.0:80/

#
#installation 
root@kali:-/week3# pip install pyftpdlib

root@kali:~/week3# python -m pyftpdlib -p 21 w
0:21, pid=12063 <<<
[I 2019-04-03 20:49:43]
[I 2019-04-03 20:49:43]
[I 2019-04-03 20:49:43] >>> starting FTP server on 0.0.0.
concurrency model: async masquerade (NAT) address: None passive ports: None

URL; ftp://192.168.56.129/
