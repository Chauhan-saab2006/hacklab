# Kali Linux WiFi Hotspot Setup (Ethernet → WiFi Sharing)

Share your Ethernet (`eth0`) internet connection over WiFi (`wlan0`) — similar to Windows Mobile Hotspot.

**Setup used:**
- Internet source: `eth0` (Ethernet)
- Hotspot broadcast: `wlan0` (WiFi)
- SSID: `MyHotspot`
- Password: `yourpassword123`

---

## 1. Check your network interfaces

```bash
nmcli device status
```

Confirms `eth0` (internet) and `wlan0` (WiFi, to be turned into hotspot) are present.

---

## 2. Create the hotspot

```bash
sudo nmcli device wifi hotspot ifname wlan0 ssid "MyHotspot" password "yourpassword123"
```

Password must be 8–63 characters (WPA2 requirement).

---

## 3. Check the hotspot's SSID / password / QR code

```bash
nmcli dev wifi show-password
```

---

## 4. Force WPA2-PSK security (fixes "incorrect password" errors)

Some devices reject NetworkManager's default security settings. Force standard WPA2-PSK/AES:

```bash
sudo nmcli connection modify Hotspot wifi-sec.key-mgmt wpa-psk
sudo nmcli connection modify Hotspot wifi-sec.psk "yourpassword123"
sudo nmcli connection up Hotspot
```

---

## 5. Ensure shared IPv4 mode (NAT + built-in DHCP server)

```bash
sudo nmcli connection modify Hotspot ipv4.method shared
sudo nmcli connection up Hotspot
```

Verify `wlan0` got its gateway IP:

```bash
ip addr show wlan0
```

Should show something like `inet 10.42.0.1/24`.

---

## 6. Enable IP forwarding (so traffic actually routes to the internet)

```bash
sudo sysctl -w net.ipv4.ip_forward=1
echo "net.ipv4.ip_forward=1" | sudo tee -a /etc/sysctl.conf
```

The `tee -a` line makes it persist across reboots.

---

## 7. Fix "Couldn't get IP address" (UFW firewall blocking DHCP)

Kali's UFW firewall blocks DHCP (port 67) and forwarding by default, which stops connected devices from getting an IP even though the hotspot itself works. Fix with:

```bash
sudo ufw allow in on wlan0 to any port 67 proto udp
sudo ufw allow in on wlan0 to any port 53 proto udp
sudo ufw route allow in on wlan0 out on eth0
sudo ufw reload
```

Then restart the hotspot:

```bash
sudo nmcli connection down Hotspot
sudo nmcli connection up Hotspot
```

---

## 8. Check for conflicting services (only if hotspot still fails)

Kali sometimes has standalone `dnsmasq`/`hostapd` installed from other tools, which can conflict with NetworkManager's built-in DHCP server:

```bash
sudo systemctl status dnsmasq hostapd
```

If either shows **active/running** outside of NetworkManager's control:

```bash
sudo systemctl stop dnsmasq hostapd
sudo systemctl disable dnsmasq hostapd
sudo nmcli connection up Hotspot
```

---

## Daily Use — Start / Stop

**Turn hotspot ON:**
```bash
sudo nmcli connection up Hotspot
```

**Turn hotspot OFF:**
```bash
sudo nmcli connection down Hotspot
```

---

## Check Status

**Active connections:**
```bash
nmcli connection show --active
```

**Device status:**
```bash
nmcli device status
```

**SSID / password / QR code:**
```bash
nmcli dev wifi show-password
```

---

## See Who's Connected

**DHCP leases (shows device name, IP, MAC):**
```bash
cat /var/lib/NetworkManager/dnsmasq-wlan0.leases
```

Format: `timestamp  MAC-address  IP-address  device-hostname  client-id`

**Live monitoring (auto-refresh every 2s):**
```bash
watch -n 2 "cat /var/lib/NetworkManager/dnsmasq-wlan0.leases"
```

**Alternative — WiFi-level stats (signal strength, connected time):**
```bash
sudo iw dev wlan0 station dump
```

---

## Change SSID / Password Later

```bash
sudo nmcli connection modify Hotspot 802-11-wireless.ssid "NewName"
sudo nmcli connection modify Hotspot wifi-sec.psk "NewPassword"
sudo nmcli connection up Hotspot
```

---

## Remove the Hotspot Profile Entirely

```bash
sudo nmcli connection delete Hotspot
```

---

## Troubleshooting Notes

- **"Incorrect password" on connecting device** → usually a stale saved network on the *client* device. Forget the network on your phone/laptop and reconnect.
- **Duplicate profiles (e.g. `Hotspot-2`)** → happens if `nmcli device wifi hotspot` is re-run instead of reusing the existing profile. Check with `nmcli connection show` and delete extras with `sudo nmcli connection delete <name>`.
- **Watch live logs while a device tries to connect** (useful for driver-level issues):
  ```bash
  sudo journalctl -u NetworkManager -f
  ```