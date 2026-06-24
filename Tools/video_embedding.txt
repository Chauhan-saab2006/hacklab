VIDEO EMBEDDING & EXTRACTION COMMANDS GUIDE

=============================== 1. MKV ATTACHMENT METHOD
===============================

Embed: mkvmerge -o output.mkv input.mp4 –attach-file secret.pdf

Extract: mkvextract attachments output.mkv

=============================== 2. METADATA (RECOMMENDED METHOD)
===============================

Encrypt: gpg -c secret.pdf

Embed: ffmpeg -i input.mp4 -metadata comment=“$(base64 secret.pdf.gpg)”
-c copy output.mp4

Extract metadata: ffmpeg -i output.mp4 -f ffmetadata metadata.txt

Decode: base64 -d metadata.txt > recovered.gpg

Decrypt: gpg recovered.gpg

=============================== 3. APPEND METHOD
===============================

Embed: cat input.mp4 secret.pdf > output.mp4

Find offset: binwalk output.mp4

Extract: dd if=output.mp4 bs=1 skip= of=recovered.pdf

=============================== 4. AUDIO STEGANOGRAPHY METHOD
===============================

Extract audio: ffmpeg -i input.mp4 -q:a 0 -map a audio.wav

Embed: steghide embed -cf audio.wav -ef secret.txt

Rebuild video: ffmpeg -i input.mp4 -i audio.wav -c:v copy -c:a aac
output.mp4
