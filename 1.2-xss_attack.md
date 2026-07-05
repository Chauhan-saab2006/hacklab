

THERE IS THREE TYPE OF XSS 
1. STORED XSS: the most dangerous type of xss this where is malicious string originates from the website's.
   this often when a website allows user input that is not sanatised(remove the "bad parts" of a user input) 
   when inserted into the database

2. REFLECTED XSS: the malicious payload is part of the victims request to the  website. the website includes this 
   payload in response back to the user . to summarise , an attacker needs to trick a victims into clicking 
   a URL to execute their malicious payload

3. DOM-BASED XSS: DOM stands for document object model and is a programming interface for html and xml document.
   it represent the pages so that pages so that program can change the document structure , style and content .
   a web page is document and this document can be either displayed in the browser or as the html source.




WE CAN DEFACE THE SITE BY ADDING SCRIPT IN INPUT BOX



if we want to get access by using hash 

┌──(kali㉿kali)-[~]
└─$ evil-winrm -i <ip> -u <domain name> -H <hash>



CROSS-SITE SCRIPTING (XSS) ATTACK:

Cross-Site Scripting (XSS) is a type of security vulnerability typically found in web applications. It allows attackers to inject malicious scripts into content from otherwise trusted websites. These scripts are then executed in the context of the victim's browser, potentially leading to data theft, session hijacking, or other malicious activities.

TYPES OF XSS ATTACKS:

1. STORED XSS:
    - Description: The most dangerous type of XSS. The malicious script is permanently stored on the target server, such as in a database, message forum, or comment field.
    - How it works: When a user accesses the affected page, the malicious script is served to their browser and executed.
    - Example: A user submits a comment containing a `<script>` tag that is not sanitized. When other users view the comment, the script executes in their browsers.
   
2. REFLECTED XSS:
    - Description: The malicious script is reflected off a web server, typically via a URL or form submission.
    - How it works: The attacker crafts a URL containing the malicious script and tricks the victim into clicking it. The server includes the script in its response, which is then executed in the victim's browser.
    - Example: A search query parameter in a URL is not properly sanitized, allowing an attacker to inject a script.

3. DOM-BASED XSS:
    - Description: The vulnerability exists in the client-side code rather than the server-side code.
    - How it works: The malicious script modifies the DOM (Document Object Model) of the web page directly in the victim's browser.
    - Example: A JavaScript function reads data from the URL and inserts it into the page without proper sanitization.

IMPACT OF XSS ATTACKS:
- Stealing sensitive information such as cookies, session tokens, or user credentials.
- Performing actions on behalf of the victim without their consent.
- Defacing websites by injecting malicious content.
- Spreading malware or phishing attacks.

PREVENTION OF XSS ATTACKS:
1. Input Validation:
    - Validate and sanitize all user inputs to ensure they do not contain malicious code.
    - Use libraries or frameworks that automatically escape special characters.

2. Output Encoding:
    - Encode data before rendering it in the browser to prevent it from being interpreted as executable code.

3. Content Security Policy (CSP):
    - Implement a CSP to restrict the sources from which scripts can be loaded and executed.

4. Use Secure Development Practices:
    - Avoid using `eval()` or similar functions in JavaScript.
    - Regularly update and patch web application frameworks and libraries.

5. HTTPOnly and Secure Cookies:
    - Use HTTPOnly cookies to prevent access to cookies via JavaScript.
    - Use Secure cookies to ensure they are only transmitted over HTTPS.

EXAMPLES OF XSS PAYLOADS:
1. `<script>alert('XSS');</script>` - A simple script to display an alert box.
2. `<img src="x" onerror="alert('XSS')">` - An image tag with an onerror event handler.
3. `<iframe src="http://malicious-site.com"></iframe>` - Embedding a malicious site.

TOOLS FOR TESTING XSS:
- Burp Suite
- OWASP ZAP
- XSSer
- Browser Developer Tools

By understanding and mitigating XSS vulnerabilities, developers can build more secure web applications and protect users from potential attacks.


















