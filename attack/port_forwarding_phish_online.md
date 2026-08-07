1.to go file
┌──(kali㉿kali)-[~]
└─$ cd /var/www/html/            

2.
┌──(kali㉿kali)-[~]
└─$ l                            

3. 
┌──(kali㉿kali)-[~]
└─$ index.html  

4.to change code
┌──(kali㉿kali)-[~]
└─$ sudo nano index.html                   

5. to check code
┌──(kali㉿kali)-[~]
└─$ cat index.html                         

6. to start server 
┌──(kali㉿kali)-[~]
└─$ sudo server apache2 start              

┌──(kali㉿kali)-[~]
└─$ sudo systemctl start apache2  

┌──(kali㉿kali)-[~]
└─$ sudo server apache2 status

7. to create phish link
┌──(kali㉿kali)-[~]
└─$ ngrok http 80  



if we want install img
┌──(kali㉿kali)-[~]
└─$ sudo apt install aria2

┌──(kali㉿kali)-[~]
└─$ aria2c <img link>

