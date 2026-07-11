# in the receiver pc 
netcat -l 1234 > SECRETS. txt

# in the transferring pc 
cat SECRETS.txt | netcat 192.168.0.49 1234 -q 0
