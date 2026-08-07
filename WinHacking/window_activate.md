# https://massgrave.dev/

# Microsoft Activation Scripts (MAS)

An open-source Windows and Office activator featuring HWID, Ohook, TSforge, and Online KMS activation methods, along with advanced troubleshooting.
Activation Methods

    Method 1: PowerShell (Recommended)
    Method 2: Traditional (Offline)

# This method is the most convenient and works on Windows 8.1, 10, and 11.

    Click the Start Menu, type PowerShell, and open it.
    Copy and paste the code below and press Enter.

" irm https://get.activated.win | iex "

3. In the menu that appears, type the number corresponding to one of the Green options.

Having trouble? (Blocked by ISP or Old Windows)

If the command is blocked:
Some ISPs block the URL. Use this command to bypass DNS blocks (Windows 10/11 only):

" iex (curl.exe -s --doh-url https://1.1.1.1/dns-query https://get.activated.win | Out-String) "

If you receive a TLS/SSL Error (Older Windows):
If you are on an old build of Windows 8.1 or 10, run this command before the main command:

"[Net.ServicePointManager]::SecurityProtocol=[Net.SecurityProtocolType]::Tls12 "

Still not working? You need to use a VPN like Cloudflare WARP or follow method 2 instead.