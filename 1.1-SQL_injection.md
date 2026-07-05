


IF WE WNT TO DUMP ALL DATA FROM SITE 

1. go to site 
2. start burpsuit library in kali 
3. start proxy burpsuit extension
4. select pretty and save item with file name in your system
5. type "sqlmap -r <file name>




SQL Injection Notes:

1. What is SQL Injection?
    - SQL Injection is a web security vulnerability that allows an attacker to interfere with the queries that 
    an application makes to its database.

2. Types of SQL Injection:
    - Classic SQL Injection
    - Blind SQL Injection
    - Union-based SQL Injection
    - Error-based SQL Injection
    - Time-based Blind SQL Injection

3. Common SQL Injection Payloads:
    - `' OR '1'='1`
    - `'; DROP TABLE users; --`
    - `admin' --`
    - `admin' #`
    - `admin'/*`

4. Tools for SQL Injection Testing:
    - sqlmap
    - Havij
    - jSQL Injection
    - Burp Suite

5. Preventing SQL Injection:
    - Use parameterized queries (prepared statements).
    - Validate and sanitize user inputs.
    - Use stored procedures.
    - Implement proper error handling.
    - Use a web application firewall (WAF).

6. Example of Parameterized Query in Python:
    ```python
    import sqlite3

    conn = sqlite3.connect('example.db')
    cursor = conn.cursor()

    # Using parameterized query to prevent SQL Injection
    username = input("Enter username: ")
    password = input("Enter password: ")
    cursor.execute("SELECT * FROM users WHERE username = ? AND password = ?", (username, password))

    result = cursor.fetchall()
    if result:
         print("Login successful!")
    else:
         print("Invalid credentials.")
    ```

7. Always test applications for vulnerabilities and fix them promptly.


Example of SQL Injection with Burp Suite:

1. Open Burp Suite and configure your browser to use Burp's proxy.
2. Navigate to the target website's login page or any input field.
3. Intercept the request using Burp Suite's Proxy tab.
4. Send the intercepted request to the Repeater tab.
5. Modify the input fields in the request with SQL Injection payloads, such as:
    - `' OR '1'='1`
    - `admin' --`
6. Send the modified request and observe the response.
7. Analyze the response to determine if the SQL Injection was successful (e.g., access granted, database error messages, etc.).

Note: Always ensure you have proper authorization before testing any website for vulnerabilities.

Examples of SQL Injection using Tools:

1. Using sqlmap:
    - Command to test for SQL Injection:
      ```
      sqlmap -u "http://example.com/vulnerable_page.php?id=1" --dbs
      ```
    - Explanation:
      This command tests the URL for SQL Injection vulnerabilities and lists the available databases.

2. Using Havij:
    - Steps:
      1. Open Havij and enter the target URL (e.g., `http://example.com/vulnerable_page.php?id=1`).
      2. Click on "Analyze" to detect SQL Injection vulnerabilities.
      3. If vulnerable, use the interface to extract database information, tables, and data.

3. Using jSQL Injection:
    - Steps:
      1. Open jSQL Injection and enter the target URL (e.g., `http://example.com/vulnerable_page.php?id=1`).
      2. Click "Inject" to start testing for SQL Injection vulnerabilities.
      3. If successful, navigate through the interface to retrieve database details, tables, and records.

Note: Always ensure you have proper authorization before using these tools to test for vulnerabilities.
