
DIRECTORY BRUTEFORCING - FINDING HIDDEN DIRECTORIES
====================================================

WHAT IS DIRECTORY BRUTEFORCING?
- Process of discovering hidden files and directories on a web server
- Uses wordlists to guess common directory/file names
- Helps find admin panels, backup files, config files, etc.

COMMON TOOLS:
1. gobuster - Fast directory/file bruteforcing tool
2. feroxbuster - Recursive content discovery tool (Rust-based)
3. dirb - Classic directory scanner
4. dirsearch - Python-based web path scanner

====================================================
GOBUSTER COMMANDS
====================================================

BASIC SYNTAX:
gobuster dir -u <URL> -w <WORDLIST>

BASIC EXAMPLES:
gobuster dir -u http://paytm.com -w /usr/share/wordlists/seclists/discovery/web-content/comman.txt
gobuster dir -u http://10.10.208.10/ -w /usr/share/wordlists/seclists/discovery/web-content/comman.txt
gobuster dir -u http://ip address/ -w /full path comman.txt

ADVANCED OPTIONS:
gobuster dir -u http://target.com -w /path/wordlist.txt -x php,html,txt -t 50 -o output.txt
  -x : Search for specific file extensions (php,html,txt,zip,bak)
  -t : Number of concurrent threads (default 10, increase for speed)
  -o : Output results to file
  -s : Status codes to show (default 200,204,301,302,307,401,403)
  -b : Status codes to exclude
  -k : Skip SSL certificate verification
  -a : Set User-Agent string
  -U : Username for Basic Auth
  -P : Password for Basic Auth

COMMON FILE EXTENSIONS TO CHECK:
gobuster dir -u http://target.com -w wordlist.txt -x php,txt,html,zip,bak,old,sql,js,json,xml

IGNORE 404 ERRORS:
gobuster dir -u http://target.com -w wordlist.txt -n

FOLLOW REDIRECTS:
gobuster dir -u http://target.com -w wordlist.txt -r

====================================================
FEROXBUSTER COMMANDS
====================================================

BASIC SYNTAX:
feroxbuster --url <URL> -w <WORDLIST>

BASIC EXAMPLES:
feroxbuster --url http://ip address/ -w /usr/share/wordlists/seclists/comman.txt
feroxbuster --url http://target.com -w /full path comman.txt
NOTE: ferox can be use without path (uses default wordlist)

ADVANCED OPTIONS:
feroxbuster -u http://target.com -w wordlist.txt -x php,html,txt -t 50 -o output.txt
  -u or --url : Target URL
  -w : Wordlist path
  -x : File extensions to search for
  -t : Number of concurrent threads
  -o : Output file
  -d : Scan depth for recursion (default: 4)
  -n : Don't scan recursively
  -k : Skip SSL certificate verification
  -s : Status codes to include (200 301 302 etc)
  -C : Status codes to exclude (404)
  --timeout : Request timeout in seconds

RECURSIVE SCANNING (automatically follows found directories):
feroxbuster -u http://target.com -w wordlist.txt -d 3

WITH AUTHENTICATION:
feroxbuster -u http://target.com -w wordlist.txt -H "Cookie: session=abc123"

SPEED UP SCAN:
feroxbuster -u http://target.com -w wordlist.txt -t 100 --timeout 5

====================================================
RECOMMENDED WORDLISTS
====================================================

SMALL/QUICK SCANS:
/usr/share/wordlists/dirb/common.txt (4600+ entries)
/usr/share/wordlists/dirbuster/directory-list-2.3-small.txt

MEDIUM SCANS:
/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
/usr/share/seclists/Discovery/Web-Content/common.txt
/usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt

COMPREHENSIVE SCANS:
/usr/share/wordlists/dirbuster/directory-list-2.3-big.txt
/usr/share/seclists/Discovery/Web-Content/raft-large-directories.txt
/usr/share/seclists/Discovery/Web-Content/raft-large-files.txt

SPECIFIC PURPOSE:
/usr/share/seclists/Discovery/Web-Content/api/*.txt (API endpoints)
/usr/share/seclists/Discovery/Web-Content/CMS/*.txt (WordPress, Joomla, etc)

====================================================
OTHER USEFUL TOOLS
====================================================

DIRB (Simple but effective):
dirb http://target.com /usr/share/wordlists/dirb/common.txt
dirb http://target.com /usr/share/wordlists/dirb/common.txt -X .php,.html,.txt

DIRSEARCH (Python-based):
dirsearch -u http://target.com -w wordlist.txt
dirsearch -u http://target.com -e php,html,js,txt
dirsearch -u http://target.com -w wordlist.txt -t 50 -r

FFUF (Fast web fuzzer):
ffuf -u http://target.com/FUZZ -w wordlist.txt
ffuf -u http://target.com/FUZZ -w wordlist.txt -mc 200,301,302,403

====================================================
TIPS & BEST PRACTICES
====================================================

1. START SMALL: Use small wordlists first (common.txt), then expand
2. THREADS: Balance speed vs detection (50-100 threads for faster scan)
3. EXTENSIONS: Target specific file types based on tech stack:
   - PHP sites: -x php,phps,php3,php4,php5,phtml,txt,bak
   - ASP sites: -x asp,aspx,config,bak
   - General: -x html,txt,zip,bak,old,sql,js
4. STATUS CODES: Focus on 200 (success), 301/302 (redirect), 403 (forbidden)
5. 403 FORBIDDEN: May still be valuable - try bypass techniques
6. SAVE OUTPUT: Always save results with -o flag for later review
7. RECURSIVE: feroxbuster auto-recurses, gobuster doesn't
8. STEALTH: Lower thread count (-t 10) for stealthier scans
9. USER-AGENT: Change UA string to avoid detection/blocking

COMMON HIDDEN DIRECTORIES TO LOOK FOR:
/admin, /administrator, /login, /backup, /uploads, /config
/api, /dev, /test, /staging, /old, /hidden, /secret
/phpmyadmin, /wp-admin, /cpanel, /.git, /.env, /robots.txt

====================================================
EXAMPLE WORKFLOW
====================================================

STEP 1 - Quick scan with common wordlist:
gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt -x php,txt,html

STEP 2 - If site is PHP, search for PHP files:
gobuster dir -u http://target.com -w /usr/share/seclists/Discovery/Web-Content/common.txt -x php,phps,bak

STEP 3 - Deep recursive scan with feroxbuster:
feroxbuster -u http://target.com -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt -x php,html,txt -t 50

STEP 4 - Check found directories for subdirectories:
gobuster dir -u http://target.com/admin -w wordlist.txt -x php,html

STEP 5 - Look for backup/config files:
gobuster dir -u http://target.com -w wordlist.txt -x bak,old,sql,zip,tar,gz

====================================================
FINDING HIDDEN LINKS IN WEBSITES
====================================================

WHAT ARE HIDDEN LINKS?
- Links not visible in normal website navigation
- URLs embedded in JavaScript, comments, or source code
- Old/deprecated pages still accessible but not linked
- API endpoints, admin panels, development pages
- Links in archived versions of the site

====================================================
METHOD 1: WEB CRAWLING/SPIDERING
====================================================

GOSPIDER (Fast Go-based spider):
gospider -s http://target.com -o output -c 10 -d 3
  -s : Target site
  -o : Output folder
  -c : Concurrent requests
  -d : Crawl depth
  -t : Timeout
  --sitemap : Include sitemap.xml
  --robots : Include robots.txt

HAKRAWLER (Simple web crawler):
echo "http://target.com" | hakrawler -d 3 -u
  -d : Depth to crawl
  -u : Show only unique URLs
  -s : Show source of URL
  -plain : Output plain URLs

KATANA (Next-gen crawler):
katana -u http://target.com -d 5 -jc -kf all -o output.txt
  -d : Depth
  -jc : JavaScript crawling
  -kf : Field to filter (all, url, path, etc)
  -o : Output file
  -ps : Passive sources (wayback, etc)

BURP SUITE SPIDER:
- Use Burp's built-in spider tool
- Right-click target > Spider this host
- Check "Spider scope" settings

====================================================
METHOD 2: JAVASCRIPT FILE ANALYSIS
====================================================

LINKFINDER (Extract endpoints from JS):
python3 linkfinder.py -i http://target.com/app.js -o output.html
python3 linkfinder.py -i http://target.com -d -o output.html
  -i : Input URL or file
  -d : Download and analyze all JS files
  -o : Output HTML file
  -r : Regex pattern for custom extraction

JSLUICE (JavaScript analysis):
jsluice urls -i http://target.com/main.js
cat urls.txt | jsluice urls

GETJS (Download all JS files):
getjs --url http://target.com --output js_files/
echo "http://target.com" | getjs

SUBJS (Subdomain and URL extraction from JS):
cat domains.txt | subjs

MANUAL JS INSPECTION:
- Open Developer Tools (F12)
- Go to Sources/Debugger tab
- Check all .js files for:
  * API endpoints (look for /api/, fetch(), axios())
  * Hidden routes (React Router, Vue Router)
  * Commented code
  * Development URLs

====================================================
METHOD 3: WAYBACK MACHINE & ARCHIVES
====================================================

WAYBACKURLS (Get archived URLs):
echo "target.com" | waybackurls > urls.txt
cat domains.txt | waybackurls | sort -u

GAU (Get All URLs from AlienVault, Wayback, Common Crawl):
gau target.com
gau target.com --threads 5 --o output.txt
echo "target.com" | gau --blacklist png,jpg,gif,css

WAYBACKPACK (Download archived versions):
waybackpack target.com -d wayback_data

MANUAL WAYBACK SEARCH:
https://web.archive.org/web/*/target.com/*

====================================================
METHOD 4: ROBOTS.TXT & SITEMAP
====================================================

CHECK ROBOTS.TXT:
curl http://target.com/robots.txt
wget http://target.com/robots.txt

Common locations in robots.txt:
- Disallow: /admin
- Disallow: /backup
- Disallow: /private
- Disallow: /dev

CHECK SITEMAP:
curl http://target.com/sitemap.xml
curl http://target.com/sitemap_index.xml
wget http://target.com/sitemap.xml

Other sitemap locations:
http://target.com/sitemap_index.xml
http://target.com/sitemap1.xml
http://target.com/post-sitemap.xml
http://target.com/page-sitemap.xml

====================================================
METHOD 5: SOURCE CODE INSPECTION
====================================================

VIEW PAGE SOURCE (Ctrl+U):
- Look for commented-out links <!-- hidden link -->
- Check for meta tags, hidden forms
- Search for href=, src=, action= attributes
- Look for data attributes (data-url, data-href)

GREP FOR URLS IN SOURCE:
curl -s http://target.com | grep -oP 'href="\K[^"]+' 
curl -s http://target.com | grep -oP 'src="\K[^"]+'
curl -s http://target.com | grep -E 'http[s]?://[^"<>[:space:]]+'

EXTRACT ALL LINKS WITH CURL:
curl -s http://target.com | grep -Eo "(http|https)://[a-zA-Z0-9./?=_-]*"

====================================================
METHOD 6: PARAMETER DISCOVERY & FUZZING
====================================================

ARJUN (HTTP parameter discovery):
arjun -u http://target.com/page.php
arjun -u http://target.com/api/user --get
arjun -u http://target.com/api/user --post

PARAM-MINER (Burp Extension):
- Install in Burp Suite
- Right-click request > "Guess params"
- Discovers hidden GET/POST parameters

X8 (Hidden parameter discovery):
x8 -u "http://target.com/page" -w params.txt
x8 -u "http://target.com/page?id=1" -w params.txt --learn-requests 100

FFUF FOR PARAMETERS:
ffuf -u http://target.com/page?FUZZ=value -w params.txt -mc 200

====================================================
METHOD 7: DIRECTORY LISTING & INDEX FILES
====================================================

CHECK FOR DIRECTORY LISTING:
curl http://target.com/uploads/
curl http://target.com/images/
curl http://target.com/files/

COMMON INDEX FILES:
http://target.com/index.php~
http://target.com/index.php.bak
http://target.com/.index.php.swp
http://target.com/index.html.old

LOOK FOR .DS_STORE (Mac):
wget http://target.com/.DS_Store
python3 dsstore_crawler.py http://target.com

LOOK FOR .GIT EXPOSURE:
http://target.com/.git/
http://target.com/.git/config
http://target.com/.git/HEAD

GitTools for dumping:
./gitdumper.sh http://target.com/.git/ output/

====================================================
METHOD 8: GOOGLE DORKING & SEARCH ENGINES
====================================================

GOOGLE DORKS FOR LINKS:
site:target.com inurl:admin
site:target.com inurl:login
site:target.com inurl:upload
site:target.com inurl:backup
site:target.com filetype:php
site:target.com intitle:"index of"
site:target.com ext:xml | ext:conf | ext:cnf | ext:reg
site:target.com inurl:wp-content
site:target.com inurl:.git

SEARCH ENGINES:
- Google: site:target.com
- Bing: site:target.com
- DuckDuckGo: site:target.com
- Shodan: hostname:target.com
- Archive.org: target.com

====================================================
METHOD 9: API & GRAPHQL DISCOVERY
====================================================

COMMON API ENDPOINTS:
/api/v1/
/api/v2/
/rest/
/graphql
/swagger
/api-docs
/api/swagger.json
/api/openapi.json
/v1/api/
/v2/api/

KITERUNNER (API endpoint discovery):
kr scan http://target.com -w routes.txt
kr brute http://target.com -w routes.txt -x 20

GRAPHQL ENUMERATION:
Check for GraphQL:
curl -X POST http://target.com/graphql -H "Content-Type: application/json" -d '{"query":"{ __schema { types { name } } }"}'

GraphQL Voyager:
https://apis.guru/graphql-voyager/

====================================================
METHOD 10: AUTOMATED LINK EXTRACTION TOOLS
====================================================

URLHUNTER (Extract URLs from web pages):
urlhunter -keywords keywords.txt -date 2020-01-01 -o found_urls.txt

XURLFIND3R (URL discovery):
xurlfind3r -d target.com

GAUPLUS (Enhanced GAU):
echo "target.com" | gauplus -random-agent -t 10

====================================================
COMPREHENSIVE LINK DISCOVERY WORKFLOW
====================================================

STEP 1 - Check basic files:
curl http://target.com/robots.txt
curl http://target.com/sitemap.xml
curl http://target.com/.git/config

STEP 2 - Spider/crawl the site:
gospider -s http://target.com -o output -c 10 -d 3
katana -u http://target.com -d 5 -jc -o katana_urls.txt

STEP 3 - Get archived URLs:
echo "target.com" | waybackurls | sort -u > wayback_urls.txt
gau target.com --threads 5 > gau_urls.txt

STEP 4 - Extract from JavaScript:
getjs --url http://target.com --output js_files/
python3 linkfinder.py -i http://target.com -d -o js_links.html

STEP 5 - Discover API endpoints:
kr scan http://target.com -w api-routes.txt
curl http://target.com/api/v1/

STEP 6 - Google dorking:
site:target.com inurl:admin OR inurl:login OR inurl:panel

STEP 7 - Combine and deduplicate all URLs:
cat *.txt | sort -u | grep target.com > all_urls.txt

STEP 8 - Filter interesting URLs:
cat all_urls.txt | grep -E "(admin|login|upload|config|backup|api)"

====================================================
TIPS FOR FINDING HIDDEN LINKS
====================================================

1. COMBINE METHODS: Use multiple tools and techniques together
2. JAVASCRIPT IS KEY: Modern sites hide most URLs in JS files
3. CHECK ARCHIVES: Wayback Machine often has old/removed pages
4. RECURSION: Found links may lead to more hidden links
5. FILTER NOISE: Ignore static assets (images, CSS) to focus on functional URLs
6. STATUS CODES: 403/401 means link exists but unauthorized
7. AUTOMATION: Create bash scripts to automate the workflow
8. LOOK FOR PATTERNS: If you find /api/v1/, try /api/v2/, /api/v3/
9. CHECK SUBDOMAINS: Different subdomains may expose different links
10. TIME-BASED: Check git commits, old JS files for historical endpoints

COMMON HIDDEN LINK PATTERNS:
/admin*, /administrator*, /backend*, /dashboard*
/api/*, /rest/*, /graphql*, /swagger*
/dev*, /test*, /staging*, /debug*
/backup*, /old*, /archive*, /temp*
/upload*, /files*, /downloads*, /attachments*
/config*, /setup*, /install*, /install.php
/.git/*, /.env*, /.DS_Store

====================================================
