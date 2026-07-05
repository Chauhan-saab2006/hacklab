KALI NETHUNTER + TERMUXX11 COMPLETE GUIDE

============================== PART 1: INSTALLATION
==============================

1.  Install Termux (F-Droid recommended)

2.  Update system: pkg update && pkg upgrade -y

3.  Install dependencies: pkg install wget git proot tar curl -y

4.  Install NetHunter: wget -O install-nethunter-termux
    https://offs.ec/2MceZWr chmod +x install-nethunter-termux bash
    install-nethunter-termux

5.  Start Kali: nethunter OR nh

============================== PART 2: BASIC COMMANDS
==============================

Enter Kali: nh

Exit Kali: exit

Update Kali: apt update && apt upgrade -y

Install tools: apt install nmap git curl -y

============================== PART 3: KEX GUI (VNC METHOD)
==============================

1.  Set password: nethunter kex passwd

2.  Start GUI: nethunter kex start –resolution 1024x768

3.  Connect via app: Address: 127.0.0.1 Port: 5901

4.  Stop GUI: nethunter kex stop

============================== PART 4: TERMUXX11 (BEST METHOD)
==============================

1.  Install packages: pkg install x11-repo -y pkg install
    termux-x11-nightly -y

2.  Start X11: termux-x11 :0 &

3.  Enter Kali: nh

4.  Set display: export DISPLAY=:0

5.  Install GUI: apt install xfce4 xfce4-goodies dbus-x11 -y

6.  Start GUI: dbus-launch startxfce4

============================== PART 5: TROUBLESHOOTING
==============================

DNS fix: echo “nameserver 8.8.8.8” > /etc/resolv.conf

Fix crashes: rm -rf ~/.cache rm -rf ~/.vnc

Restart GUI: nethunter kex stop nethunter kex start

Check running services: ps aux

============================== PART 6: IMPORTANT NOTES
==============================

-   Use Termux from F-Droid
-   Keep storage free (8GB recommended)
-   Disable battery optimization
-   Use split screen for stability
-   CLI is more stable than GUI

============================== END OF GUIDE
==============================
