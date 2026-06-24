┌──(apma㉿kali)-[~]
└─$ sudo su                                            
[sudo] password for apma: 
┌──(root㉿kali)-[/home/apma]
└─# apt install ani-cli      
The following packages were automatically installed and are no longer required:
  curlftpfs      libconfig-inifiles-perl  libmpeg2encpp-2.1-0t64  libpostproc58      libswscale8         python3-aiocache        python3-yaswfp
  libaudio2      libfuse2t64              libmplex2-2.1-0t64      librubberband2     libvdpau-va-gl1     python3-aiomcache       ruby-unf-ext
  libavfilter10  libgav1-1                libmupdf25.1            libsnmp40t64       mesa-vdpau-drivers  python3-fs              vdpau-driver-all
  libavformat61  libmjpegutils-2.1-0t64   libpocketsphinx3        libsphinxbase3t64  pocketsphinx-en-us  python3-wapiti-arsenic
Use 'sudo apt autoremove' to remove them.

Installing:
  ani-cli

Installing dependencies:
  aria2  ffmpeg  fzf  libaria2-0  libavdevice62  liblua5.2-0  libsixel1  libva-wayland2  mpv  python3-mutagen  yt-dlp

Suggested packages:
  rofi  ffmpeg-doc  libcuda1  python-mutagen-doc  libfribidi-bin  | bidiv

Summary:
  Upgrading: 0, Installing: 12, Removing: 0, Not Upgrading: 11
  Download size: 9,107 kB
  Space needed: 31.0 MB / 15.8 GB available

Continue? [Y/n] Y
Get:1 http://http.kali.org/kali kali-rolling/main amd64 libavdevice62 amd64 7:8.0.1-3+b1 [106 kB]
Get:2 http://http.kali.org/kali kali-rolling/main amd64 liblua5.2-0 amd64 5.2.4-3+b4 [116 kB]
Get:3 http://http.kali.org/kali kali-rolling/main amd64 libsixel1 amd64 1.10.5-1+b1 [111 kB]
Get:4 http://mirrors.esto.network/kali kali-rolling/main amd64 libva-wayland2 amd64 2.23.0-1 [22.1 kB]
Get:5 http://http.kali.org/kali kali-rolling/main amd64 mpv amd64 0.41.0-2+b1 [1,372 kB]
Get:7 http://http.kali.org/kali kali-rolling/main amd64 ffmpeg amd64 7:8.0.1-3+b1 [2,045 kB]
Get:6 http://http.kali.org/kali kali-rolling/main amd64 fzf amd64 0.67.0-1+b1 [1,526 kB]                                                                    
Get:8 http://http.kali.org/kali kali-rolling/main amd64 libaria2-0 amd64 1.37.0+debian-4 [1,158 kB]                                                         
Get:9 http://http.kali.org/kali kali-rolling/main amd64 aria2 amd64 1.37.0+debian-4 [370 kB]                                                                
Get:10 http://kali.download/kali kali-rolling/main amd64 ani-cli all 4.10-1 [13.5 kB]                                                                       
Get:11 http://kali.download/kali kali-rolling/main amd64 python3-mutagen all 1.47.0-1 [136 kB]                                                              
Get:12 http://kali.download/kali kali-rolling/main amd64 yt-dlp all 2026.01.31-1 [2,131 kB]                                                                 
Fetched 9,107 kB in 19s (482 kB/s)                                                                                                                          
Selecting previously unselected package libavdevice62:amd64.
(Reading database… 438072 files and directories currently installed.)
Preparing to unpack …/00-libavdevice62_7%3a8.0.1-3+b1_amd64.deb…
Unpacking libavdevice62:amd64 (7:8.0.1-3+b1)…
Selecting previously unselected package liblua5.2-0:amd64.
Preparing to unpack …/01-liblua5.2-0_5.2.4-3+b4_amd64.deb…
Unpacking liblua5.2-0:amd64 (5.2.4-3+b4)…
Selecting previously unselected package libsixel1:amd64.
Preparing to unpack …/02-libsixel1_1.10.5-1+b1_amd64.deb…
Unpacking libsixel1:amd64 (1.10.5-1+b1)…
Selecting previously unselected package libva-wayland2:amd64.
Preparing to unpack …/03-libva-wayland2_2.23.0-1_amd64.deb…
Unpacking libva-wayland2:amd64 (2.23.0-1)…
Selecting previously unselected package mpv.
Preparing to unpack …/04-mpv_0.41.0-2+b1_amd64.deb…
Unpacking mpv (0.41.0-2+b1)…
Selecting previously unselected package fzf.
Preparing to unpack …/05-fzf_0.67.0-1+b1_amd64.deb…
Unpacking fzf (0.67.0-1+b1)…
Selecting previously unselected package ffmpeg.
Preparing to unpack …/06-ffmpeg_7%3a8.0.1-3+b1_amd64.deb…
Unpacking ffmpeg (7:8.0.1-3+b1)…
Selecting previously unselected package libaria2-0:amd64.
Preparing to unpack …/07-libaria2-0_1.37.0+debian-4_amd64.deb…
Unpacking libaria2-0:amd64 (1.37.0+debian-4)…
Selecting previously unselected package aria2.
Preparing to unpack …/08-aria2_1.37.0+debian-4_amd64.deb…
Unpacking aria2 (1.37.0+debian-4)…
Selecting previously unselected package ani-cli.
Preparing to unpack …/09-ani-cli_4.10-1_all.deb…
Unpacking ani-cli (4.10-1)…
Selecting previously unselected package python3-mutagen.
Preparing to unpack …/10-python3-mutagen_1.47.0-1_all.deb…
Unpacking python3-mutagen (1.47.0-1)…
Selecting previously unselected package yt-dlp.
Preparing to unpack …/11-yt-dlp_2026.01.31-1_all.deb…
Unpacking yt-dlp (2026.01.31-1)…
Setting up libaria2-0:amd64 (1.37.0+debian-4)…
Setting up aria2 (1.37.0+debian-4)…
Setting up python3-mutagen (1.47.0-1)…
Setting up libavdevice62:amd64 (7:8.0.1-3+b1)…
Setting up libsixel1:amd64 (1.10.5-1+b1)…
Setting up yt-dlp (2026.01.31-1)…
Setting up libva-wayland2:amd64 (2.23.0-1)…
Setting up fzf (0.67.0-1+b1)…
Setting up liblua5.2-0:amd64 (5.2.4-3+b4)…
Setting up ffmpeg (7:8.0.1-3+b1)…
Setting up mpv (0.41.0-2+b1)…
Setting up ani-cli (4.10-1)…
Processing triggers for desktop-file-utils (0.28-1)…
Processing triggers for hicolor-icon-theme (0.18-2)…
Processing triggers for libc-bin (2.42-5)…
Processing triggers for man-db (2.13.1-1)…
Processing triggers for kali-menu (2026.1.3)…
                                                                                                                                                                                                                                                                                                                     
┌──(root㉿kali)-[/home/apma]
└─# ani-cli list               
youtube Links Fetched
wixmp Links Fetched
hianime Links Fetched
                                                                                                                                                             
┌──(root㉿kali)-[/home/apma]
└─# ani-cli -q 480 --dub jujutsu kaisen
Checking dependencies...
                                                                                                                                                             
┌──(root㉿kali)-[/home/apma]
└─# 
> sudo ani-cli --update
