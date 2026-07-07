# Nikto Web Server Scanner

**Nikto** is an active, open-source web server scanner that performs comprehensive tests against web servers to identify potential security vulnerabilities, misconfigurations, and outdated software. It checks for over 6,700 potentially dangerous files and CGIs, examines server configuration items (such as missing security headers, enabled HTTP options, and server info disclosure), and detects outdated versions of server daemons and plugins. Designed for speed and thoroughness, Nikto is a staple reconnaissance tool in penetration testing and security auditing, though its high volume of requests makes it noisy and easily detectable by modern Intrusion Detection Systems (IDS).



┌──(kali㉿kali)-[~]
└─$ nikto -h https://tesla.com
- Nikto v2.6.0
---------------------------------------------------------------------------
+ Target IP:          2.18.49.207
+ Target Hostname:    tesla.com
+ Target Port:        443
---------------------------------------------------------------------------
+ SSL Info:           Subject:  /CN=tesla.com
                      CN:       tesla.com
                      SAN:      tesla.com
                      Ciphers:  TLS_AES_256_GCM_SHA384
                      Issuer:   /C=US/O=Let's Encrypt/CN=YR2
+ Platform:           Unknown
+ Start Time:         2026-07-07 19:21:22 (GMT5.5)
---------------------------------------------------------------------------
+ Server: AkamaiGHost
+ Multiple IPs found: 2.18.49.207, 2.18.52.207, 2.18.53.207, 2.18.55.207, 2.18.54.207, 2.18.50.207, 2.18.48.207, 2.18.51.207, 23.40.100.207, 23.7.244.207, 64:ff9b::1728:64cf, 64:ff9b::212:31cf, 64:ff9b::212:30cf, 64:ff9b::1707:f4cf, 64:ff9b::212:33cf, 64:ff9b::212:32cf, 64:ff9b::212:37cf, 64:ff9b::212:36cf, 64:ff9b::212:35cf, 64:ff9b::212:34cf
+ ERROR: Failed to check for updates: 403
+ [999100] /: Uncommon header(s) 'x-ak-cache' found, with contents: Error from child.
+ [999100] /: Uncommon header(s) 'x-reference-error' found, with contents: 18.543c717.1783432283.76e565b4.
+ No CGI Directories found (use '-C all' to force check all possible dirs). CGI tests skipped.
+ [013587] /: Suggested security header missing: referrer-policy. See: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy
+ [013587] /: Suggested security header missing: x-content-type-options. See: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Content-Type-Options
+ [013587] /: Suggested security header missing: content-security-policy. See: https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP
+ ERROR: *** Error limit (20) reached for host, giving up. Last error: opening stream: ssl connect failed. ***
+ ERROR: *** Consider using mitmproxy to avoid TLS fingerprinting. ***
- STATUS: Completed 118 requests (~2% complete, ~3.8 hours left): currently in plugin 'Site Files'
- STATUS: Running average: Not enough data.
+ Scan terminated: 20 errors and 5 items reported on the remote host
+ End Time:           2026-07-07 19:25:07 (GMT5.5) (225 seconds)
---------------------------------------------------------------------------
+ 1 host(s) tested
                                                                              
┌──(kali㉿kali)-[~]
└─$ 
                                                                          