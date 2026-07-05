COMPLETE GUIDE: PASSWORD-PROTECTED ZIP IN LINUX

======================================== 1. INTRODUCTION
======================================== This guide explains how to
create, manage, and securely use password-protected archives in Linux
using zip, 7z, and gpg.

======================================== 2. INSTALLATION
======================================== Debian/Ubuntu: sudo apt update
sudo apt install zip unzip p7zip-full gnupg

CentOS/RHEL: sudo yum install zip unzip p7zip gnupg

Arch: sudo pacman -S zip unzip p7zip gnupg

======================================== 3. USING ZIP (BASIC)
========================================

Create encrypted zip: zip -e archive.zip file.txt

Multiple files: zip -e archive.zip file1.txt file2.txt

Directory: zip -er archive.zip folder/

Extract: unzip archive.zip

List contents: unzip -l archive.zip

======================================== 4. ZIP SECURITY NOTES
======================================== - Uses weak ZipCrypto
encryption - Vulnerable to brute-force attacks - Not recommended for
sensitive data

Avoid: zip -P password archive.zip file.txt

Reason: - Password visible in history and process list

======================================== 5. USING 7Z (RECOMMENDED)
========================================

Create archive: 7z a archive.7z file.txt

With password: 7z a -p archive.7z file.txt

Encrypt filenames: 7z a -p -mhe=on archive.7z file.txt

Extract: 7z x archive.7z

======================================== 6. USING GPG (STRONGEST)
========================================

Encrypt file: gpg –symmetric file.txt

Decrypt: gpg file.txt.gpg

======================================== 7. PASSWORD BEST PRACTICES
======================================== - Minimum 12–16 characters -
Mix uppercase, lowercase, numbers, symbols - Avoid dictionary words -
Use password manager

======================================== 8. AUTOMATION EXAMPLE
========================================

#!/bin/bash zip -er backup.zip /home/user/data

======================================== 9. PENTESTING INSIGHT
======================================== Weak zip encryption can be
cracked using tools like: - fcrackzip - john the ripper

(Use only in legal environments)

======================================== 10. TROUBLESHOOTING
========================================

zip not found: Install zip package

Permission denied: Use sudo or check file permissions

Archive corrupted: Try: zip -FF archive.zip –out fixed.zip

======================================== 11. COMPARISON
========================================

zip → Weak encryption 7z → AES-256 (recommended) gpg → AES-256 (best
security)

======================================== END OF GUIDE
========================================


2️⃣ Compress the PDF first (recommended)

Reduce the PDF size.

zip book.zip "The Art of Invisibility.pdf"

Then embed:

steghide embed -ef book.zip -cf bigimage.jpg
