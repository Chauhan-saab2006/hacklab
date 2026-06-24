Microsoft Windows [Version 10.0.26100.3323]
(c) Microsoft Corporation. All rights reserved.

C:\Users\lenovo>netsh
netsh>wlan show profile

Profiles on interface Wi-Fi:

Group policy profiles (read only)
---------------------------------
    <None>

User profiles
-------------
    All User Profile     : Redmi
    All User Profile     : Redmi Note 7S
    All User Profile     : Manish chauhan
    All User Profile     : Apma's Z Fold3
    All User Profile     : realme NARZO N61
    All User Profile     : vivo 1904
    All User Profile     : vivo 1820
    All User Profile     : Airtel_rohi_6698
    All User Profile     : Airtel_Softline Computers5G

netsh>wlan show profile "Airtel_rohi_6698" key=clear

Profile Airtel_rohi_6698 on interface Wi-Fi:
=======================================================================

Applied: All User Profile

Profile information
-------------------
    Version                : 1
    Type                   : Wireless LAN
    Name                   : Airtel_rohi_6698
    Control options        :
        Connection mode    : Connect manually
        Network broadcast  : Connect only if this network is broadcasting
        AutoSwitch         : Do not switch to other networks
        MAC Randomization  : Disabled

Connectivity settings
---------------------
    Number of SSIDs        : 1
    SSID name              : "Airtel_rohi_6698"
    Network type           : Infrastructure
    Radio type             : [ Any Radio Type ]
    Vendor extension          : Not present

Security settings
-----------------
    Authentication         : WPA3-Personal
    Cipher                 : GCMP-256
    Authentication         : WPA3-Personal
    Cipher                 : GCMP
    Authentication         : WPA3-Personal
    Cipher                 : CCMP
    Authentication         : WPA2-Personal
    Cipher                 : GCMP
    Authentication         : WPA2-Personal
    Cipher                 : CCMP
    Security key           : Present
    Key Content            : air83164

Cost settings
-------------
    Cost                   : Unrestricted
    Congested              : No
    Approaching Data Limit : No
    Over Data Limit        : No
    Roaming                : No
    Cost Source            : Default

netsh>
