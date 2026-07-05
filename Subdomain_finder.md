1️⃣ Using Subfinder (Most Common)

Install
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
Run
subfinder -d example.com
Save results
subfinder -d example.com -o subdomains.txt

Example output

api.example.com
mail.example.com
dev.example.com
blog.example.com
2️⃣ Using Amass (More Comprehensive)

Install
sudo apt install amass
Run
amass enum -d example.com
3️⃣ Using Assetfinder

Assetfinder is simple and fast.

Install
go install github.com/tomnomnom/assetfinder@latest
Run
assetfinder --subs-only example.com
4️⃣ Using DNS brute force

dnsrecon -d example.com -t brt
5️⃣ Using crt.sh (Certificate Transparency)

You can pull subdomains from SSL certificates:

curl -s https://crt.sh/?q=%25.example.com&output=json | jq -r '.[].name_value' | sort -u
🔥 Pro Tip (What Real Recon Pipelines Look Like)

Most professionals combine tools:

subfinder -d example.com | tee subs.txt
assetfinder --subs-only example.com >> subs.txt
amass enum -passive -d example.com >> subs.txt
sort -u subs.txt

Subdomain enumeration → find api.example.com, dev.example.com

Directory brute forcing → find /admin, /login, /backup.zip

dirb works on the second step, after you already have a domain or subdomain.

1️⃣ Basic DIRB Usage
Syntax
dirb http://example.com

Example:

dirb http://example.com /usr/share/wordlists/dirb/common.txt

Output example:

+ http://example.com/admin
+ http://example.com/login
+ http://example.com/backup

This means those directories exist on the server.

2️⃣ Install DIRB (if not installed)
sudo apt install dirb
3️⃣ Scan a Subdomain

Once you find a subdomain like:

dev.example.com

Then run:

dirb http://dev.example.com

or

dirb https://dev.example.com
4️⃣ Use Custom Wordlist

Wordlists are important.

Example:

dirb https://example.com /usr/share/wordlists/dirb/big.txt

Common wordlists:

/usr/share/wordlists/dirb/common.txt
/usr/share/wordlists/dirb/big.txt
/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
5️⃣ Ignore Certain Status Codes
dirb http://example.com -N 403
6️⃣ Save Results
dirb http://example.com -o result.txt
🔥 Real Hacker Workflow (Simple)

Step 1 — Find subdomains
Use tools like:

Subfinder

OWASP Amass

Step 2 — Check which are alive

cat subs.txt | httpx

Step 3 — Run DIRB

dirb https://target.com
dirb https://dev.target.com
dirb https://api.target.com
🧠 Pro Tip (Used in Bug Bounty)

Instead of dirb, many professionals now prefer:

Gobuster

ffuf

They are much faster and more powerful.

Example:

ffuf -u https://example.com/FUZZ -w wordlist.txt

