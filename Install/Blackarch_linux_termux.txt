
Step-by-Step: Installing BlackArch Tools in Termux
1. Install Termux and Required Packages :
pkg update
pkg install proot-distro
2. Install Arch Linux:
proot-distro install archlinux
proot-distro login archlinux
Now you're inside a fake root Arch Linux environment.

3. Inside Arch: Add BlackArch:
curl -O https://blackarch.org/strap.sh
chmod +x strap.sh
./strap.sh

4,
pacman -Syyu
pacman -S blackarch-tools

tools of blackarch linux in termux:
[root@localhost ~]# pacman -Sg | grep blackarch-
blackarch-webapp
blackarch-fuzzer
blackarch-scanner
blackarch-proxy
blackarch-windows
blackarch-dos
blackarch-disassembler
blackarch-sniffer
blackarch-voip
blackarch-fingerprint
blackarch-networking
blackarch-recon
blackarch-cracker
blackarch-exploitation
blackarch-spoof
blackarch-forensic
blackarch-crypto
blackarch-backdoor
blackarch-defensive
blackarch-wireless
blackarch-automation
blackarch-radio
blackarch-binary
blackarch-reversing
blackarch-mobile
blackarch-malware
blackarch-code-audit
blackarch-social
blackarch-honeypot
blackarch-misc
blackarch-wordlist
blackarch-config
blackarch-decompiler
blackarch-debugger
blackarch-bluetooth
blackarch-database
blackarch-automobile
blackarch-hardware
blackarch-nfc
blackarch-tunnel
blackarch-drone
blackarch-unpacker
blackarch-firmware
blackarch-keylogger
blackarch-stego
blackarch-packer
blackarch-anti-forensic
blackarch-ids
[root@localhost ~]#
