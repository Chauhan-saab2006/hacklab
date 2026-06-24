┌──(kali㉿kali)-[~]
└─$ cd /etc/           
                                                                                                                             
┌──(kali㉿kali)-[/etc]
└─$ ls
adduser.conf              firebird            libnl-3          paperspecs         snmp
alsa                      firefox-esr         libpaper.d       passwd             speech-dispatcher
alternatives              fonts               lightdm          passwd-            sqlmap
apache2                   freetds             lighttpd         perl               ssh
apparmor                  fstab               locale.alias     php                ssl
apparmor.d                fuse.conf           locale.conf      plymouth           sslsplit
apt                       gai.conf            locale.gen       polkit-1           strongswan.conf
arp-scan                  geoclue             localtime        postgresql         strongswan.d
avahi                     ghostscript         logcheck         postgresql-common  stunnel
bash.bashrc               glvnd               login.defs       powershell-empire  subgid
bash_completion           gnome-system-tools  logrotate.conf   ppp                subgid-
bash_completion.d         gophish             logrotate.d      profile            subuid
bindresvport.blacklist    gprofng.rc          macchanger       profile.d          subuid-
binfmt.d                  groff               machine-id       protocols          subversion
bluetooth                 group               magic            proxychains4.conf  sudo.conf
ca-certificates           group-              magic.mime       pulse              sudoers
ca-certificates.conf      grub.d              mailcap          python2.7          sudoers.d
chatscripts               gshadow             mailcap.order    python3            sudo_logsrvd.conf
chromium                  gshadow-            manpath.config   python3.12         supercat
chromium.d                gss                 matplotlibrc     python3.13         sv
cifs-utils                gtk-2.0             mime.types       radcli             sysctl.d
cloud                     gtk-3.0             minicom          rc0.d              sysstat
colord                    guymager            miredo           rc1.d              systemd
console-setup             gvm                 miredo.conf      rc2.d              terminfo
cracklib                  hdparm.conf         mke2fs.conf      rc3.d              texmf
credstore                 host.conf           ModemManager     rc4.d              theHarvester
credstore.encrypted       hostname            modprobe.d       rc5.d              tightvncserver.conf
cron.d                    hosts               modules          rc6.d              timidity
cron.daily                hosts.allow         modules-load.d   rcS.d              tmpfiles.d
cron.hourly               hosts.deny          mosquitto        reader.conf.d      ts.conf
cron.monthly              idmapd.conf         motd             rearj.cfg          ucf.conf
crontab                   ifplugd             mtab             redis              udev
cron.weekly               ImageMagick-7       mysql            redsocks.conf      udisks2
cron.yearly               inetsim             nanorc           request-key.conf   ufw
cryptsetup-initramfs      init.d              netconfig        request-key.d      unicornscan
cryptsetup-nuke-password  initramfs-tools     netsniff-ng      resolv.conf        updatedb.conf
crypttab                  inputrc             network          responder          update-motd.d
cupshelpers               insserv.conf.d      NetworkManager   rmt                UPower
dbus-1                    ipp-usb             networks         rpc                usb_modeswitch.conf
dconf                     ipsec.conf          nfs.conf         runit              usb_modeswitch.d
debconf.conf              ipsec.d             nfs.conf.d       samba              vconsole.conf
debian_version            ipsec.secrets       nftables.conf    sane.d             vdpau_wrapper.cfg
default                   issue               nginx            scalpel            vim
deluser.conf              issue.net           nikto.conf       screenrc           vpnc
depmod.d                  java-21-openjdk     nsisconf.nsh     sddm.conf.d        vulkan
dhcp                      john                nsswitch.conf    searchsploit_rc    wgetrc
dhcpcd.conf               kali-menu           ODBCDataSources  security           wireshark
dictionaries-common       kernel              odbc.ini         selinux            wpa_supplicant
dns2tcpd.conf             keyutils            odbcinst.ini     sensors3.conf      X11
doc-base                  kismet              openal           sensors.d          xattr.conf
dpkg                      ldap                OpenCL           services           xdg
e2scrub.conf              ld.so.cache         openni2          sgml               xfce4
eac                       ld.so.conf          opensc           shadow             xml
emacs                     ld.so.conf.d        openvas          shadow-            xrdp
environment               legion.conf         openvpn          shells             zsh
environment.d             libao.conf          opt              skel               zsh_command_not_found
ethertypes                libaudit.conf       os-release       smartd.conf
ettercap                  libblockdev         pam.conf         smartmontools
feroxbuster               libccid_Info.plist  pam.d            smi.conf
                                                                                                                             
┌──(kali㉿kali)-[/etc]
└─$ sudo nano /etc/proxychains4.conf
[sudo] password for kali: 
                                                                                                                             
change socks4 to socks5
and 
remove the hash from dynamic and add to strict

┌──(kali㉿kali)-[/etc]
└─$ sudo apt update         
Hit:1 http://http.kali.org/kali kali-rolling InRelease
7 packages can be upgraded. Run 'apt list --upgradable' to see them.
                            

┌──(kali㉿kali)-[/etc]
└─$ sudo apt install tor


┌──(kali㉿kali)-[/etc]
└─$ sudo systemctl start tor
                                                                                                                             
┌──(kali㉿kali)-[/etc]
└─$ sudo systemctl status tor
● tor.service - Anonymizing overlay network for TCP (multi-instance-master)
     Loaded: loaded (/usr/lib/systemd/system/tor.service; disabled; preset: disabled)
     Active: active (exited) since Thu 2025-04-24 05:14:21 EDT; 37s ago
 Invocation: 1b962b31e41f452588eca4545f13cf32
    Process: 27945 ExecStart=/bin/true (code=exited, status=0/SUCCESS)
   Main PID: 27945 (code=exited, status=0/SUCCESS)
   Mem peak: 2M
        CPU: 13ms

Apr 24 05:14:21 kali systemd[1]: Starting tor.service - Anonymizing overlay network for TCP (multi-instance-master)...
Apr 24 05:14:21 kali systemd[1]: Finished tor.service - Anonymizing overlay network for TCP (multi-instance-master).
                                                                                                                             
┌──(kali㉿kali)-[/etc]
└─$ proxychains4 firefox
