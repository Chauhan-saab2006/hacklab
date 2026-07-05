┌──(root㉿kali)-[~]
└─# whatweb tesla.com
http://tesla.com [403 Forbidden] Akamai-Global-Host, Country[EUROPEAN UNION][EU], HTTPServer[AkamaiGHost], IP[2.18.49.207], Title[Access Denied], UncommonHeaders[x-reference-error,x-ak-cache,permissions-policy]
https://tesla.com [403 Forbidden] Akamai-Global-Host, Country[EUROPEAN UNION][EU], HTTPServer[AkamaiGHost], IP[2.18.48.207], Strict-Transport-Security[max-age=15768000], Title[Access Denied], UncommonHeaders[x-reference-error,x-ak-cache,permissions-policy]
                                                                                                                                                      
┌──(root㉿kali)-[~]
└─# whatweb -v tesla.com
WhatWeb report for http://tesla.com
Status    : 403 Forbidden
Title     : Access Denied
IP        : 2.18.52.207
Country   : EUROPEAN UNION, EU

Summary   : Akamai-Global-Host, HTTPServer[AkamaiGHost], UncommonHeaders[x-reference-error,x-ak-cache,permissions-policy]

Detected Plugins:
[ Akamai-Global-Host ]
        Akamai-Global-Host HTTPd 

        Website     : https://www.akamai.com

[ HTTPServer ]
        HTTP server header string. This plugin also attempts to 
        identify the operating system from the server header. 

        String       : AkamaiGHost (from server string)

[ UncommonHeaders ]
        Uncommon HTTP server headers. The blacklist includes all 
        the standard headers and many non standard but common ones. 
        Interesting but fairly common headers should have their own 
        plugins, eg. x-powered-by, server and x-aspnet-version. 
        Info about headers can be found at www.http-stats.com 

        String       : x-reference-error,x-ak-cache,permissions-policy (from headers)

HTTP Headers:
        HTTP/1.1 403 Forbidden
        Server: AkamaiGHost
        Mime-Version: 1.0
        Content-Type: text/html
        Content-Length: 357
        Expires: Sun, 05 Jul 2026 07:52:05 GMT
        X-Reference-Error: 18.88cd017.1783237925.e0321023
        Date: Sun, 05 Jul 2026 07:52:05 GMT
        Connection: close
        X-AK-Cache: Error from child
        Permissions-Policy: interest-cohort=()

WhatWeb report for https://tesla.com
Status    : 403 Forbidden
Title     : Access Denied
IP        : 2.18.53.207
Country   : EUROPEAN UNION, EU

Summary   : Akamai-Global-Host, HTTPServer[AkamaiGHost], Strict-Transport-Security[max-age=15768000], UncommonHeaders[x-reference-error,x-ak-cache,permissions-policy]

Detected Plugins:
[ Akamai-Global-Host ]
        Akamai-Global-Host HTTPd 

        Website     : https://www.akamai.com

[ HTTPServer ]
        HTTP server header string. This plugin also attempts to 
        identify the operating system from the server header. 

        String       : AkamaiGHost (from server string)

[ Strict-Transport-Security ]
        Strict-Transport-Security is an HTTP header that restricts 
        a web browser from accessing a website without the security 
        of the HTTPS protocol. 

        String       : max-age=15768000

[ UncommonHeaders ]
        Uncommon HTTP server headers. The blacklist includes all 
        the standard headers and many non standard but common ones. 
        Interesting but fairly common headers should have their own 
        plugins, eg. x-powered-by, server and x-aspnet-version. 
        Info about headers can be found at www.http-stats.com 

        String       : x-reference-error,x-ak-cache,permissions-policy (from headers)

HTTP Headers:
        HTTP/1.1 403 Forbidden
        Server: AkamaiGHost
        Mime-Version: 1.0
        Content-Type: text/html
        Content-Length: 357
        Expires: Sun, 05 Jul 2026 07:52:06 GMT
        X-Reference-Error: 18.88cd017.1783237925.e0321c0d
        Date: Sun, 05 Jul 2026 07:52:06 GMT
        Connection: close
        Strict-Transport-Security: max-age=15768000
        X-AK-Cache: Error from child
        Permissions-Policy: interest-cohort=()

                                                                                                                                                      
┌──(root㉿kali)-[~]
└─# 
