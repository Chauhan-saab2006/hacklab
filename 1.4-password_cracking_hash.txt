FEATURES             ENCRIPTION                        HASHING 

process            two-way (can be reversed)      one-way (irreversible)

purple             protects Confidentiality       ensures integrity

key Required       yes, for both Execution and        NO  
                            decryption

Output             variable lenght (depend on     fixed lenght (e.g., 256-bit for SHA-256)
                           data size)

use Cases          security data in transit       verifying data integrity (e.g., passwords) 
                   (e.g., emails, files )

example            AES, RSA, Blowfish             MD5, SHA-1, SHA-256
algorithms




MD5 : 
      is site is used to create hash of password

Crackstation :
              is site is used to decode hash in  password      

hashes.com :
            is site is used to decode hash in  password

also 
┌──(kali㉿kali)-[~]
└─$ hashcat -h 

1st we save the hash in file
┌──(kali㉿kali)-[~]
└─$ echo "4d1ac3081dd751a8a83ddb5d6230f8be">hash.txt

2nd we check file save or not
┌──(kali㉿kali)-[~]
└─$ cat hash.txt 
4d1ac3081dd751a8a83ddb5d6230f8be

3rd we check the type of hash 
┌──(kali㉿kali)-[~]
└─$ hash-identifier                                             
   #########################################################################
   #     __  __                     __           ______    _____           #
   #    /\ \/\ \                   /\ \         /\__  _\  /\  _ `\         #
   #    \ \ \_\ \     __      ____ \ \ \___     \/_/\ \/  \ \ \/\ \        #
   #     \ \  _  \  /'__`\   / ,__\ \ \  _ `\      \ \ \   \ \ \ \ \       #
   #      \ \ \ \ \/\ \_\ \_/\__, `\ \ \ \ \ \      \_\ \__ \ \ \_\ \      #
   #       \ \_\ \_\ \___ \_\/\____/  \ \_\ \_\     /\_____\ \ \____/      #
   #        \/_/\/_/\/__/\/_/\/___/    \/_/\/_/     \/_____/  \/___/  v1.2 #
   #                                                             By Zion3R #
   #                                                    www.Blackploit.com #
   #                                                   Root@Blackploit.com #
   #########################################################################
--------------------------------------------------
 HASH: provide hash
┌──(kali㉿kali)-[~]
└─$ hashcat -h | grep MD5                                       
      0 | MD5                                                        | Raw Hash
   5100 | Half MD5                                                   | Raw Hash
     50 | HMAC-MD5 (key = $pass)                                     | Raw Hash authenticated
     60 | HMAC-MD5 (key = $salt)                                     | Raw Hash authenticated
  11900 | PBKDF2-HMAC-MD5                                            | Generic KDF
  11400 | SIP digest authentication (MD5)                            | Network Protocol
   5300 | IKE-PSK MD5                                                | Network Protocol
  25100 | SNMPv3 HMAC-MD5-96                                         | Network Protocol
  25000 | SNMPv3 HMAC-MD5-96/HMAC-SHA1-96                            | Network Protocol
  10200 | CRAM-MD5                                                   | Network Protocol
   4800 | iSCSI CHAP authentication, MD5(CHAP)                       | Network Protocol
  19000 | QNX /etc/shadow (MD5)                                      | Operating System
   2410 | Cisco-ASA MD5                                              | Operating System
   2400 | Cisco-PIX MD5                                              | Operating System
    500 | md5crypt, MD5 (Unix), Cisco-IOS $1$ (MD5)                  | Operating System


4th we check the mode 
┌──(kali㉿kali)-[~]
└─$ hashcat -h | grep <hash name>  

5th we use this command to decode the hash
┌──(kali㉿kali)-[~]
└─$ hashcat -a 0 -m 1000 hash.txt /usr/share/wardlists/rocky.txt

we have to use correct mode like (1000) etc



WE HAVE ALTERNATIVE john -h (john the ripper)

┌──(kali㉿kali)-[~]
└─$ john hash.txt
but it take so much time so better way is to Provide word list

┌──(kali㉿kali)-[~]
└─$ echo "417dbe2827ac185505d69c5d0762e6cd" >hash.txt

┌──(kali㉿kali)-[~]
└─$ john hash.txt --format=NT --wordlist=/usr/share/wordlists/rockyou.txt

┌──(kali㉿kali)-[~]
└─$ john hash.txt --fork=4 --wordlist=/usr/share/wordlists/rockyou.txt



┌──(kali㉿kali)-[~]
└─$ hash-identifier                                             
   #########################################################################
   #     __  __                     __           ______    _____           #
   #    /\ \/\ \                   /\ \         /\__  _\  /\  _ `\         #
   #    \ \ \_\ \     __      ____ \ \ \___     \/_/\ \/  \ \ \/\ \        #
   #     \ \  _  \  /'__`\   / ,__\ \ \  _ `\      \ \ \   \ \ \ \ \       #
   #      \ \ \ \ \/\ \_\ \_/\__, `\ \ \ \ \ \      \_\ \__ \ \ \_\ \      #
   #       \ \_\ \_\ \___ \_\/\____/  \ \_\ \_\     /\_____\ \ \____/      #
   #        \/_/\/_/\/__/\/_/\/___/    \/_/\/_/     \/_____/  \/___/  v1.2 #
   #                                                             By Zion3R #
   #                                                    www.Blackploit.com #
   #                                                   Root@Blackploit.com #
   #########################################################################
--------------------------------------------------
 HASH: provide hash


┌──(kali㉿kali)-[~]
└─$ hashcat -h | grep MD5                                       
      0 | MD5                                                        | Raw Hash
   5100 | Half MD5                                                   | Raw Hash
     50 | HMAC-MD5 (key = $pass)                                     | Raw Hash authenticated
     60 | HMAC-MD5 (key = $salt)                                     | Raw Hash authenticated
  11900 | PBKDF2-HMAC-MD5                                            | Generic KDF
  11400 | SIP digest authentication (MD5)                            | Network Protocol
   5300 | IKE-PSK MD5                                                | Network Protocol
  25100 | SNMPv3 HMAC-MD5-96                                         | Network Protocol
  25000 | SNMPv3 HMAC-MD5-96/HMAC-SHA1-96                            | Network Protocol
  10200 | CRAM-MD5                                                   | Network Protocol
   4800 | iSCSI CHAP authentication, MD5(CHAP)                       | Network Protocol
  19000 | QNX /etc/shadow (MD5)                                      | Operating System
   2410 | Cisco-ASA MD5                                              | Operating System
   2400 | Cisco-PIX MD5                                              | Operating System
    500 | md5crypt, MD5 (Unix), Cisco-IOS $1$ (MD5)                  | Operating System
  11100 | PostgreSQL CRAM (MD5)                                      | Database Server
  16400 | CRAM-MD5 Dovecot                                           | FTP, HTTP, SMTP, LDAP Server
  24900 | Dahua Authentication MD5                                   | FTP, HTTP, SMTP, LDAP Server
   1600 | Apache $apr1$ MD5, md5apr1, MD5 (APR)                      | FTP, HTTP, SMTP, LDAP Server
   9700 | MS Office <= 2003 $0/$1, MD5 + RC4                         | Document
   9710 | MS Office <= 2003 $0/$1, MD5 + RC4, collider #1            | Document
   9720 | MS Office <= 2003 $0/$1, MD5 + RC4, collider #2            | Document
  30000 | Python Werkzeug MD5 (HMAC-MD5 (key = $salt))               | Framework
  22500 | MultiBit Classic .key (MD5)                                | Cryptocurrency Wallet
  Wordlist + Rules | MD5   | hashcat -a 0 -m 0 example0.hash example.dict -r rules/best64.rule
  Brute-Force      | MD5   | hashcat -a 3 -m 0 example0.hash ?a?a?a?a?a?a
  Combinator       | MD5   | hashcat -a 1 -m 0 example0.hash example.dict example.dict
                           


if we don't find the mode of hash
go to the  https://hashcat.net/wiki/doku.php?id=example_hashes this web site to chech hash



for change the passwod find lenght use this command
1st use this to change lenght
┌──(kali㉿kali)-[~]
└─$ cat rockyou.txt | awk -F/ ' length($NF) == 4 ' > rockyoumodified.txt
cat: rockyou.txt: No such file or directory

if it show not fond . to solve this                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ gunzip /usr/share/wordlists/rockyou.txt.gz
gzip: /usr/share/wordlists/rockyou.txt.gz: No such file or directory

and provide complete path                                                                                                                             
┌──(kali㉿kali)-[~]
└─$ cat /usr/share/wordlists/rockyou.txt | awk -F/ ' length($NF) == 4 ' > rockyoumodified.txt
awk: cmd. line:1: (FILENAME=- FNR=602044) warning: Invalid multibyte data detected. There may be a mismatch between your data and your locale

to check change succesfull or not
┌──(kali㉿kali)-[~]
└─$ head rockyoumodified.txt  
love
1234
pink
poop
baby
sexy
alex
/dev/null
star
mike
      


      CRACKING ZIP FILE PASSWORD:

      1. Install fcrackzip:
         ┌──(kali㉿kali)-[~]
         └─$ sudo apt install fcrackzip

      2. Use fcrackzip with a wordlist:
         ┌──(kali㉿kali)-[~]
         └─$ fcrackzip -v -u -D -p /usr/share/wordlists/rockyou.txt target.zip

         - `-v`: Verbose mode.
         - `-u`: Try to decompress the file to verify the password.
         - `-D`: Use a dictionary attack.
         - `-p`: Specify the path to the wordlist.

      3. If the wordlist is compressed, extract it first:
         ┌──(kali㉿kali)-[~]
         └─$ gunzip /usr/share/wordlists/rockyou.txt.gz

      ---

      CRACKING SSH PRIVATE KEY PASSWORD:

      1. Install John the Ripper:
         ┌──(kali㉿kali)-[~]
         └─$ sudo apt install john

      2. Convert the SSH private key to a format John can use:
         ┌──(kali㉿kali)-[~]
         └─$ ssh2john id_rsa > id_rsa.hash

      3. Use John with a wordlist to crack the password:
         ┌──(kali㉿kali)-[~]
         └─$ john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa.hash

      4. Check the cracked password:
         ┌──(kali㉿kali)-[~]
         └─$ john --show id_rsa.hash





         DETAILED NOTES FOR CRACKING PASSWORDS:

         1. **Understanding Hashes**:
            - Hashes are one-way cryptographic functions used to ensure data integrity.
            - Examples: MD5, SHA-1, SHA-256.
            - Hashes cannot be reversed but can be cracked using brute force or dictionary attacks.

         2. **Identifying the Hash Type**:
            - Save the hash in a file:
              ```bash
              echo "your_hash_here" > hash.txt
              ```
            - Use `hash-identifier` or online tools to identify the hash type:
              ```bash
              hash-identifier
              ```

         3. **Using Hashcat**:
            - Install Hashcat if not already installed:
              ```bash
              sudo apt install hashcat
              ```
            - Check available modes for the hash type:
              ```bash
              hashcat -h | grep <hash_name>
              ```
            - Crack the hash using a wordlist:
              ```bash
              hashcat -a 0 -m <mode> hash.txt /usr/share/wordlists/rockyou.txt
              ```
            - Replace `<mode>` with the correct mode for your hash type.

         4. **Using John the Ripper**:
            - Install John the Ripper:
              ```bash
              sudo apt install john
              ```
            - Crack the hash using a wordlist:
              ```bash
              john hash.txt --wordlist=/usr/share/wordlists/rockyou.txt
              ```
            - For faster cracking, use multiple forks:
              ```bash
              john hash.txt --fork=4 --wordlist=/usr/share/wordlists/rockyou.txt
              ```

         5. **Cracking ZIP File Passwords**:
            - Install `fcrackzip`:
              ```bash
              sudo apt install fcrackzip
              ```
            - Use a dictionary attack with a wordlist:
              ```bash
              fcrackzip -v -u -D -p /usr/share/wordlists/rockyou.txt target.zip
              ```

         6. **Cracking SSH Private Key Passwords**:
            - Install John the Ripper:
              ```bash
              sudo apt install john
              ```
            - Convert the SSH private key to a format John can use:
              ```bash
              ssh2john id_rsa > id_rsa.hash
              ```
            - Crack the password using a wordlist:
              ```bash
              john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa.hash
              ```
            - Display the cracked password:
              ```bash
              john --show id_rsa.hash
              ```

         7. **Modifying Wordlists**:
            - Extract the `rockyou.txt` wordlist if compressed:
              ```bash
              gunzip /usr/share/wordlists/rockyou.txt.gz
              ```
            - Filter the wordlist for specific lengths:
              ```bash
              cat /usr/share/wordlists/rockyou.txt | awk 'length == <desired_length>' > modified_wordlist.txt
              ```
            - Verify the modified wordlist:
              ```bash
              head modified_wordlist.txt
              ```

         8. **Additional Resources**:
            - Use online tools like Crackstation or Hashes.com to decode hashes.
            - Refer to the Hashcat example hashes page for more details:
              [https://hashcat.net/wiki/doku.php?id=example_hashes](https://hashcat.net/wiki/doku.php?id=example_hashes)

         9. **Tips**:
            - Always use the correct mode for your hash type in Hashcat.
            - Provide a comprehensive wordlist for better chances of cracking.
            - Use tools like `hash-identifier` to identify unknown hash types.




insta hack
┌──(kali㉿kali)-[~]
└─$ cd instainsane
                                                                                                                             
┌──(kali㉿kali)-[~/instainsane]
└─$ chmod +x instainsane.sh
                                                                                                                             
┌──(kali㉿kali)-[~/instainsane]
└─$ sudo ./instainsane.sh
[sudo] password for kali: 
  _              _            _____                                  
 (_) _ __   ___ | |_   __ _   \_   \ _ __   ___   __ _  _ __    ___  
 | || '_ \ / __|| __| / _` |   / /\/| '_ \ / __| / _` || '_ \  / _ \ 
 | || | | |\__ \| |_ | (_| |/\/ /_  | | | |\__ \| (_| || | | ||  __/ 
 |_||_| |_||___/ \__| \__,_|\____/  |_| |_||___/ \__,_||_| |_| \___| 

  Instagram Brute Forcer v1.0, Author: @thelinuxchoice (Github/IG)  

Username account: ashwanichauhan868
Password List (Enter to default list): pass.list
[*] Starting Tor on port: 9051
[*] Starting Tor on port: 9052
[*] Starting Tor on port: 9053
[*] Starting Tor on port: 9054
[*] Starting Tor on port: 9055
[*] Checking Tor connection on port: 9051...OK!
[*] Checking Tor connection on port: 9052...OK!
[*] Checking Tor connection on port: 9053...OK!
[*] Checking Tor connection on port: 9054...OK!
[*] Checking Tor connection on port: 9055...OK!

[*] Starting...


