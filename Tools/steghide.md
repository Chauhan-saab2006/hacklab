┌──(apma㉿kali)-[~/hack]
└─$ sudo apt install steghide
[sudo] password for apma: 
The following packages were automatically installed and are no longer required:
  curlftpfs                libfuse2t64             libmupdf25.1      libsphinxbase3t64   python3-aiocache        ruby-unf-ext
  libaudio2                libgav1-1               libpocketsphinx3  libswscale8         python3-aiomcache       vdpau-driver-all
  libavfilter10            libmjpegutils-2.1-0t64  libpostproc58     libvdpau-va-gl1     python3-fs
  libavformat61            libmpeg2encpp-2.1-0t64  librubberband2    mesa-vdpau-drivers  python3-wapiti-arsenic
  libconfig-inifiles-perl  libmplex2-2.1-0t64      libsnmp40t64      pocketsphinx-en-us  python3-yaswfp
Use 'sudo apt autoremove' to remove them.

Installing:
  steghide
                                                                                                                                                 
Installing dependencies:
  libmcrypt4  libmhash2
                                                                                                                                                 
Suggested packages:
  libmcrypt-dev  mcrypt

Summary:
  Upgrading: 0, Installing: 3, Removing: 0, Not Upgrading: 31
  Download size: 309 kB
  Space needed: 916 kB / 15.3 GB available

Continue? [Y/n] Y
Get:1 http://http.kali.org/kali kali-rolling/main amd64 libmcrypt4 amd64 2.5.8-8+b1 [72.1 kB]
Get:3 http://kali.download/kali kali-rolling/main amd64 steghide amd64 0.5.1-15 [144 kB]
Get:2 http://mirrors.esto.network/kali kali-rolling/main amd64 libmhash2 amd64 0.9.9.9-11 [93.2 kB]
Fetched 309 kB in 2s (140 kB/s)   
Selecting previously unselected package libmcrypt4:amd64.
(Reading database… 439572 files and directories currently installed.)
Preparing to unpack …/libmcrypt4_2.5.8-8+b1_amd64.deb…
Unpacking libmcrypt4:amd64 (2.5.8-8+b1)…
Selecting previously unselected package libmhash2:amd64.
Preparing to unpack …/libmhash2_0.9.9.9-11_amd64.deb…
Unpacking libmhash2:amd64 (0.9.9.9-11)…
Selecting previously unselected package steghide.
Preparing to unpack …/steghide_0.5.1-15_amd64.deb…
Unpacking steghide (0.5.1-15)…
Setting up libmhash2:amd64 (0.9.9.9-11)…
Setting up libmcrypt4:amd64 (2.5.8-8+b1)…
Setting up steghide (0.5.1-15)…
Processing triggers for libc-bin (2.42-5)…
Processing triggers for man-db (2.13.1-1)…
Processing triggers for kali-menu (2026.1.3)…
                                                                                                                                                 
┌──(apma㉿kali)-[~/hack]
└─$ steghide --help                                                               
steghide version 0.5.1

the first argument must be one of the following:
 embed, --embed          embed data
 extract, --extract      extract data
 info, --info            display information about a cover- or stego-file
   info <filename>       display information about <filename>
 encinfo, --encinfo      display a list of supported encryption algorithms
 version, --version      display version information
 license, --license      display steghide's license
 help, --help            display this usage information

embedding options:
 -ef, --embedfile        select file to be embedded
   -ef <filename>        embed the file <filename>
 -cf, --coverfile        select cover-file
   -cf <filename>        embed into the file <filename>
 -p, --passphrase        specify passphrase
   -p <passphrase>       use <passphrase> to embed data
 -sf, --stegofile        select stego file
   -sf <filename>        write result to <filename> instead of cover-file
 -e, --encryption        select encryption parameters
   -e <a>[<m>]|<m>[<a>]  specify an encryption algorithm and/or mode
   -e none               do not encrypt data before embedding
 -z, --compress          compress data before embedding (default)
   -z <l>                 using level <l> (1 best speed...9 best compression)
 -Z, --dontcompress      do not compress data before embedding
 -K, --nochecksum        do not embed crc32 checksum of embedded data
 -N, --dontembedname     do not embed the name of the original file
 -f, --force             overwrite existing files
 -q, --quiet             suppress information messages
 -v, --verbose           display detailed information

extracting options:
 -sf, --stegofile        select stego file
   -sf <filename>        extract data from <filename>
 -p, --passphrase        specify passphrase
   -p <passphrase>       use <passphrase> to extract data
 -xf, --extractfile      select file name for extracted data
   -xf <filename>        write the extracted data to <filename>
 -f, --force             overwrite existing files
 -q, --quiet             suppress information messages
 -v, --verbose           display detailed information

options for the info command:
 -p, --passphrase        specify passphrase
   -p <passphrase>       use <passphrase> to get info about embedded data

To embed emb.txt in cvr.jpg: steghide embed -cf cvr.jpg -ef emb.txt
To extract embedded data from stg.jpg: steghide extract -sf stg.jpg
                                                                                                                                                 
┌──(apma㉿kali)-[~/hack]
└─$
                                                                                                                                                 
┌──(apma㉿kali)-[~/hack]
└─$ steghide embed -ef "Penetration Testing.pdf" -cf Anime-Boy-Wallpaper-Desktop.jpg
Enter passphrase: 
Re-Enter passphrase: 
embedding "Penetration Testing.pdf" in "Anime-Boy-Wallpaper-Desktop.jpg"... done
                                                                                                                                                 
┌──(apma㉿kali)-[~/hack]
└─$ steghide extract -sf Anime-Boy-Wallpaper-Desktop.jpg
Enter passphrase: 
wrote extracted data to "Penetration Testing.pdf".
                                                                                                                                                 
┌──(apma㉿kali)-[~/hack]
└─$ 



1️⃣ Method 1 — Hide data in a frame (image steganography)
A video is just many images (frames). So you can hide the data in one frame.

Step 1 — Extract frames
Use FFmpeg:

ffmpeg -i video.mp4 frames/frame_%04d.jpg
This extracts frames like:

frame_0001.jpg
frame_0002.jpg
Step 2 — Embed the PDF in a frame
Use Steghide:

steghide embed -cf frame_0001.jpg -ef secret.pdf
Step 3 — Rebuild the video
ffmpeg -framerate 30 -i frames/frame_%04d.jpg -c:v libx264 output.mp4
Now the video contains a frame with hidden data.
