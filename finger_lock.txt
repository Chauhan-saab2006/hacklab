                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo apt update
sudo apt install fprintd libpam-fprintd
[sudo] password for kali: 
Hit:1 https://brave-browser-apt-release.s3.brave.com stable InRelease
Hit:2 http://http.kali.org/kali kali-rolling InRelease                       
Hit:3 https://us-central1-apt.pkg.dev/projects/antigravity-auto-updater-dev antigravity-debian InRelease
All packages are up to date.    
The following packages were automatically installed and are no longer required:
  libfltk-images1.3t64  libsimdutf31         node-ip
  libfltk1.3t64         libsvtav1enc2        node-uuid
  libicu76              libteamdctl0         openjdk-21-jre
  libio-pty-perl        libunibreak6         openjdk-21-jre-headless
  libipc-run-perl       libxmlsec1-1         postgresql-common-dev
  libpostal-data        libxmlsec1-openssl1  python3-pluginbase
  libpostal1            libzxing3            python3-pysnmp4
  libsdl2-classic       node-depd
Use 'sudo apt autoremove' to remove them.

Installing:
  fprintd  libpam-fprintd

Installing dependencies:
  libfprint-2-2

Summary:
  Upgrading: 0, Installing: 3, Removing: 0, Not Upgrading: 0
  Download size: 442 kB
  Space needed: 2,117 kB / 127 GB available

Continue? [Y/n] Y
Get:1 http://kali.download/kali kali-rolling/main amd64 libfprint-2-2 amd64 1:1.94.10-1 [302 kB]
Get:2 http://http.kali.org/kali kali-rolling/main amd64 fprintd amd64 1.94.5-4+b1 [127 kB]
Get:3 http://http.kali.org/kali kali-rolling/main amd64 libpam-fprintd amd64 1.94.5-4+b1 [14.1 kB]
Fetched 442 kB in 2s (218 kB/s)           
Selecting previously unselected package libfprint-2-2.
(Reading database… 498346 files and directories currently installed.)
Preparing to unpack …/libfprint-2-2_1%3a1.94.10-1_amd64.deb…
Unpacking libfprint-2-2 (1:1.94.10-1)…
Selecting previously unselected package fprintd.
Preparing to unpack …/fprintd_1.94.5-4+b1_amd64.deb…
Unpacking fprintd (1.94.5-4+b1)…
Selecting previously unselected package libpam-fprintd:amd64.
Preparing to unpack …/libpam-fprintd_1.94.5-4+b1_amd64.deb…
Unpacking libpam-fprintd:amd64 (1.94.5-4+b1)…
Setting up libfprint-2-2 (1:1.94.10-1)…
Setting up fprintd (1.94.5-4+b1)…
fprintd.service is a disabled or a static unit, not starting it.
Setting up libpam-fprintd:amd64 (1.94.5-4+b1)…
Processing triggers for libc-bin (2.42-13)…
Processing triggers for man-db (2.13.1-1)…
Processing triggers for dbus (1.16.2-4)…
Processing triggers for udev (260.1-1)…
Processing triggers for kali-menu (2026.2.3)…
                                                                              
┌──(kali㉿kali)-[~]
└─$ fprintd-enroll
Using device /net/reactivated/Fprint/Device/0
Enrolling right-index-finger finger.
Enroll result: enroll-stage-passed
Enroll result: enroll-disconnected
                                                                              
┌──(kali㉿kali)-[~]
└─$ fprintd-enroll
Using device /net/reactivated/Fprint/Device/0
Enrolling right-index-finger finger.
Enroll result: enroll-stage-passed
Enroll result: enroll-unknown-error
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo systemctl restart fprintd
                                                                              
┌──(kali㉿kali)-[~]
└─$ fprintd-enroll
Using device /net/reactivated/Fprint/Device/0
Enrolling right-index-finger finger.
Enroll result: enroll-unknown-error
                                                                              
┌──(kali㉿kali)-[~]
└─$ journalctl -u fprintd --no-pager | tail -30
May 13 21:44:14 kali systemd[1]: Starting fprintd.service - Fingerprint Authentication Daemon...
May 13 21:44:14 kali systemd[1]: Started fprintd.service - Fingerprint Authentication Daemon.
May 13 21:44:20 kali fprintd[4099]: Device reported an error during enroll: The driver encountered a protocol error with the device.
May 13 21:44:29 kali fprintd[4099]: Device reported an error during enroll: Calibration failed!
May 13 21:44:54 kali systemd[1]: Stopping fprintd.service - Fingerprint Authentication Daemon...
May 13 21:44:54 kali systemd[1]: fprintd.service: Deactivated successfully.
May 13 21:44:54 kali systemd[1]: Stopped fprintd.service - Fingerprint Authentication Daemon.
May 13 21:44:54 kali systemd[1]: Starting fprintd.service - Fingerprint Authentication Daemon...
May 13 21:44:54 kali systemd[1]: Started fprintd.service - Fingerprint Authentication Daemon.
May 13 21:45:01 kali fprintd[4306]: Device reported an error during identify for enroll: Calibration failed!
                                                                              
┌──(kali㉿kali)-[~]
└─$ fprintd-enroll left-index-finger
Using device /net/reactivated/Fprint/Device/0
Enrolling right-index-finger finger.
Enroll result: enroll-stage-passed
Enroll result: enroll-unknown-error
                                                                              
┌──(kali㉿kali)-[~]
└─$ 
                                                                             
┌──(kali㉿kali)-[~]
└─$ fprintd-enroll
Using device /net/reactivated/Fprint/Device/0
Enrolling right-index-finger finger.
Enroll result: enroll-retry-scan
Enroll result: enroll-stage-passed
Enroll result: enroll-retry-scan
Enroll result: enroll-stage-passed
Enroll result: enroll-retry-scan
Enroll result: enroll-stage-passed
Enroll result: enroll-retry-scan
Enroll result: enroll-retry-scan
Enroll result: enroll-swipe-too-short
Enroll result: enroll-stage-passed
Enroll result: enroll-retry-scan
Enroll result: enroll-stage-passed
Enroll result: enroll-completed
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo pam-auth-update
[sudo] password for kali: 
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo pam-auth-update
                                                                              
┌──(kali㉿kali)-[~]
└─$ sudo ls
Crucix	 Documents  genmon-scripts  hacklab  Pictures  Public	  Videos
Desktop  Downloads  GhostTrack	    Music    Projects  Templates  wallpapers
                                                                              
┌──(kali㉿kali)-[~]
└─$ 

