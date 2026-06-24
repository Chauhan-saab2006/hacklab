┌──(apma㉿kali)-[~/hacking_tools]
└─$ sudo apt install exif -y     
[sudo] password for apma: 
The following packages were automatically installed and are no longer required:
  curlftpfs      libavformat61            libgav1-1               libmplex2-2.1-0t64  libpostproc58   libsphinxbase3t64  mesa-vdpau-drivers  python3-aiomcache       python3-yaswfp
  libaudio2      libconfig-inifiles-perl  libmjpegutils-2.1-0t64  libmupdf25.1        librubberband2  libswscale8        pocketsphinx-en-us  python3-fs              ruby-unf-ext
  libavfilter10  libfuse2t64              libmpeg2encpp-2.1-0t64  libpocketsphinx3    libsnmp40t64    libvdpau-va-gl1    python3-aiocache    python3-wapiti-arsenic  vdpau-driver-all
Use 'sudo apt autoremove' to remove them.

Installing:
  exif

Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 11
  Download size: 58.0 kB
  Space needed: 343 kB / 15.5 GB available

Get:1 http://mirrors.esto.network/kali kali-rolling/main amd64 exif amd64 0.6.22-4 [58.0 kB]
Fetched 58.0 kB in 3s (22.3 kB/s)                        
Selecting previously unselected package exif.
(Reading database… 439533 files and directories currently installed.)
Preparing to unpack …/exif_0.6.22-4_amd64.deb…
Unpacking exif (0.6.22-4)…
Setting up exif (0.6.22-4)…
Processing triggers for man-db (2.13.1-1)…
Processing triggers for kali-menu (2026.1.3)…
                                                                                                                                                                                                                                           
┌──(apma㉿kali)-[~/hacking_tools]
└─$ exiftool '/home/apma/hacking_tools/Anime-Boy-Wallpaper-Desktop.jpg'
ExifTool Version Number         : 13.50
File Name                       : Anime-Boy-Wallpaper-Desktop.jpg
Directory                       : /home/apma/hacking_tools
File Size                       : 185 kB
File Modification Date/Time     : 2026:02:26 17:34:29+05:30
File Access Date/Time           : 2026:02:26 18:56:39+05:30
File Inode Change Date/Time     : 2026:02:26 17:34:29+05:30
File Permissions                : -rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Data Mining                     : Allowed
Profile CMM Type                : Linotronic
Profile Version                 : 2.1.0
Profile Class                   : Display Device Profile
Color Space Data                : RGB
Profile Connection Space        : XYZ
Profile Date Time               : 1998:02:09 06:49:00
Profile File Signature          : acsp
Primary Platform                : Microsoft Corporation
CMM Flags                       : Not Embedded, Independent
Device Manufacturer             : Hewlett-Packard
Device Model                    : sRGB
Device Attributes               : Reflective, Glossy, Positive, Color
Rendering Intent                : Media-Relative Colorimetric
Connection Space Illuminant     : 0.9642 1 0.82491
Profile Creator                 : Hewlett-Packard
Profile ID                      : 0
Profile Copyright               : Copyright (c) 1998 Hewlett-Packard Company
Profile Description             : sRGB IEC61966-2.1
Media White Point               : 0.95045 1 1.08905
Media Black Point               : 0 0 0
Red Matrix Column               : 0.43607 0.22249 0.01392
Green Matrix Column             : 0.38515 0.71687 0.09708
Blue Matrix Column              : 0.14307 0.06061 0.7141
Device Mfg Desc                 : IEC http://www.iec.ch
Device Model Desc               : IEC 61966-2.1 Default RGB colour space - sRGB
Viewing Cond Desc               : Reference Viewing Condition in IEC61966-2.1
Viewing Cond Illuminant         : 19.6445 20.3718 16.8089
Viewing Cond Surround           : 3.92889 4.07439 3.36179
Viewing Cond Illuminant Type    : D50
Luminance                       : 76.03647 80 87.12462
Measurement Observer            : CIE 1931
Measurement Backing             : 0 0 0
Measurement Geometry            : Unknown
Measurement Flare               : 0.999%
Measurement Illuminant          : D65
Technology                      : Cathode Ray Tube Display
Red Tone Reproduction Curve     : (Binary data 2060 bytes, use -b option to extract)
Green Tone Reproduction Curve   : (Binary data 2060 bytes, use -b option to extract)
Blue Tone Reproduction Curve    : (Binary data 2060 bytes, use -b option to extract)
Image Width                     : 3840
Image Height                    : 2160
Encoding Process                : Progressive DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 3840x2160
Megapixels                      : 8.3
                                                                                                                                                                                                               
┌──(apma㉿kali)-[~/hacking_tools]
└─$ 


Add a simple message:
exiftool -Comment="Hi" image.jpg
Or a longer message:

exiftool -ImageDescription="This is a secret test message" image.jpg
If you don’t want a backup file:

exiftool -overwrite_original -Comment="Hi" image.jpg
Check it:
exiftool image.jpg
You’ll see your message in:




🧹 Remove ALL metadata from an image
exiftool -all= image.jpg
That’s it.

What this does:
-all= → deletes every metadata tag

Creates a backup automatically (image.jpg_original)

🚫 Remove metadata WITHOUT creating a backup
By default, exiftool makes a backup file. If you don’t want that:

exiftool -all= -overwrite_original image.jpg
Now it edits the file in place.

🗂 Remove metadata from multiple images
exiftool -all= -overwrite_original *.jpg
Or entire directory:
