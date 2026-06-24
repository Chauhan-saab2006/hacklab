# 8__

parallels kali-linux-2022-2)-[~/go/bin]
> sudo apt install httprobe

-(parallels® kali-linux-2022-2)
> cat yahoo.urls | httprobe

(mod® phdsec)-[~]
> sudo apt install subilist3r

-(mod®phdsec)-[~]
$ sublist3r -h

mod@phdsec:~
> sublist3r -d yahoo.com
            Subjstor
Searching now in Baidu.. I
Searching now in Yahoo..
Searching now in Google
Searching now
Searching now in Virustotal..
Searching now in ThreatCrowd..
Searching now in SSL Certificates

(mod® phdsec)-[~]
> amass -h

mod phdsec)-[~]
amass enum -d yahoo.com

-(mod® phdsec)-[~]
amass enum -passive -d yahoo.com

# SubDomain Find using wordlist

-(parallels®kali-linux-2022-2)-[~]
> ffuf -u https://FUZZ.yahoo.com/ -w /usr/share/wordlists/dirb/common.txt -p 1

-(parallels kali-linux-2022-2)-[~]
> ffuf -u https://FUZZ.yahoo.com/ -W /usr/share/wordlists/dirb/common.txt -p 1 -fc 301

-(parallels®kali-linux-2022-2)-[~]
> ffuf -u https://yahoo.com/FUZZ -w /usr/share/wordlists/dirb/common.txt -p 1 -fc 301

(parallels kali-linux-2022-2)-[~]
> ffuf -u https://api.yahoo.com/FUZZ -w /usr/share/wordlists/dirb/common.txt

(parallels®kali-linux-2022-2)-[~] 
> dirb https://yahoo.com

