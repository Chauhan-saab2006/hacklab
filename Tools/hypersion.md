                                                     
┌──(root㉿kali)-[/]
└─# sudo apt update
sudo apt install hyperion
Get:1 http://kali.download/kali kali-rolling InRelease [41.5 kB]
Err:1 http://kali.download/kali kali-rolling InRelease
  Sub-process /usr/bin/sqv returned an error code (1), error message is: Missing key 827C8569F2518CC677FECA1AED65462EC8D5E4C5, which is needed to verify signature.
3 packages can be upgraded. Run 'apt list --upgradable' to see them.
Warning: An error occurred during the signature verification. The repository is not updated and the previous index files will be used. OpenPGP signature verification failed: http://kali.download/kali kali-rolling InRelease: Sub-process /usr/bin/sqv returned an error code (1), error message is: Missing key 827C8569F2518CC677FECA1AED65462EC8D5E4C5, which is needed to verify signature.
Warning: Failed to fetch http://http.kali.org/kali/dists/kali-rolling/InRelease  Sub-process /usr/bin/sqv returned an error code (1), error message is: Missing key 827C8569F2518CC677FECA1AED65462EC8D5E4C5, which is needed to verify signature.
Warning: Some index files failed to download. They have been ignored, or old ones used instead.
hyperion is already the newest version (2.0-0kali4).
hyperion set to manually installed.
The following packages were automatically installed and are no longer required:
  icu-devtools     libpoppler145
  libabsl20230802  libpython3.12-minimal
  libdnnl3         libpython3.12-stdlib
  libflac12t64     libpython3.12t64
  libfuse3-3       libxnnpack0
  libgeos3.13.0    python3-setproctitle
  libglapi-mesa    python3.12-tk
  libicu-dev       ruby-zeitwerk
  liblbfgsb0       strongswan
  libopenh264-7
Use 'sudo apt autoremove' to remove them.

Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 3
                                                     
┌──(root㉿kali)-[/]
└─#  

                                                     
┌──(root㉿kali)-[/]
└─#  

                                                     
┌──(root㉿kali)-[/]
└─# git clone https://github.com/nullsecuritynet/tools.git  
fatal: destination path 'tools' already exists and is not an empty directory.
                                                     
┌──(root㉿kali)-[/]
└─# cd tools/binary/hyperion
                                                     
┌──(root㉿kali)-[/tools/binary/hyperion]
└─# sudo apt update
sudo apt install mingw-w64
Get:1 http://kali.download/kali kali-rolling InRelease [41.5 kB]
Err:1 http://kali.download/kali kali-rolling InRelease
  Sub-process /usr/bin/sqv returned an error code (1), error message is: Missing key 827C8569F2518CC677FECA1AED65462EC8D5E4C5, which is needed to verify signature.
Fetched 41.5 kB in 6s (6,423 B/s)
3 packages can be upgraded. Run 'apt list --upgradable' to see them.
Warning: An error occurred during the signature verification. The repository is not updated and the previous index files will be used. OpenPGP signature verification failed: http://kali.download/kali kali-rolling InRelease: Sub-process /usr/bin/sqv returned an error code (1), error message is: Missing key 827C8569F2518CC677FECA1AED65462EC8D5E4C5, which is needed to verify signature.
Warning: Failed to fetch http://http.kali.org/kali/dists/kali-rolling/InRelease  Sub-process /usr/bin/sqv returned an error code (1), error message is: Missing key 827C8569F2518CC677FECA1AED65462EC8D5E4C5, which is needed to verify signature.
Warning: Some index files failed to download. They have been ignored, or old ones used instead.
The following packages were automatically installed and are no longer required:
  icu-devtools     libpoppler145
  libabsl20230802  libpython3.12-minimal
  libdnnl3         libpython3.12-stdlib
  libflac12t64     libpython3.12t64
  libfuse3-3       libxnnpack0
  libgeos3.13.0    python3-setproctitle
  libglapi-mesa    python3.12-tk
  libicu-dev       ruby-zeitwerk
  liblbfgsb0       strongswan
  libopenh264-7
Use 'sudo apt autoremove' to remove them.

Installing:
  mingw-w64
                                                     
Installing dependencies:
  g++-mingw-w64
  g++-mingw-w64-i686                                 
  g++-mingw-w64-i686-posix                           
  g++-mingw-w64-i686-win32                           
  g++-mingw-w64-x86-64                               
  g++-mingw-w64-x86-64-posix                         
  g++-mingw-w64-x86-64-win32                         
  gcc-mingw-w64                                      
  gcc-mingw-w64-i686                                 
  gcc-mingw-w64-i686-posix                           
  gcc-mingw-w64-i686-posix-runtime                   
  gcc-mingw-w64-x86-64                               
  gcc-mingw-w64-x86-64-posix                         
  gcc-mingw-w64-x86-64-posix-runtime                 
                                                     
Suggested packages:
  gcc-14-locales

Summary:
  Upgrading: 0, Installing: 15, Removing: 0, Not Upgrading: 3
  Download size: 162 MB
  Space needed: 677 MB / 55.2 GB available

Continue? [Y/n] y
Get:1 http://http.kali.org/kali kali-rolling/main amd64 gcc-mingw-w64-i686-posix-runtime amd64 14.2.0-19+27+b1 [12.3 MB]
