# Arping User Guide

## Overview

`arping` sends ARP (Address Resolution Protocol) requests on a local
network to discover whether a device with a specific IPv4 address is
present and to learn its MAC address.

## Installation

``` bash
sudo apt update
sudo apt install iputils-arping
```

## Verify Installation

``` bash
arping -V
```

## Basic Syntax

``` bash
arping [options] <IP-address>
```

## How ARP Works

1.  Your computer asks: "Who has 192.168.1.10?"
2.  The device with that IP replies with its MAC address.
3.  `arping` displays the reply.

## Common Commands

Ping a local device:

``` bash
sudo arping 192.168.1.1
```

Specify interface:

``` bash
sudo arping -I wlan0 192.168.1.1
```

Send only 5 requests:

``` bash
sudo arping -c 5 192.168.1.1
```

Quit after first reply:

``` bash
sudo arping -f 192.168.1.1
```

Broadcast ARP:

``` bash
sudo arping -b 192.168.1.1
```

Duplicate Address Detection:

``` bash
sudo arping -D -I wlan0 192.168.1.100
```

## Important Options

  Option   Description
  -------- -----------------------------
  -I       Network interface
  -c       Number of packets
  -i       Interval between packets
  -f       Stop after first reply
  -b       Broadcast ARP
  -D       Duplicate Address Detection
  -V       Show version

## Finding Local Devices

Find your subnet:

``` bash
ip route
```

Example:

``` text
192.168.1.0/24 dev wlan0
```

Discover all live hosts:

``` bash
sudo nmap -sn 192.168.1.0/24
```

or

``` bash
sudo arp-scan --interface=wlan0 --localnet
```

## arping vs ping

  ping                        arping
  --------------------------- -----------------------------
  Uses ICMP                   Uses ARP
  Works across the Internet   Works only on the local LAN
  Tests IP connectivity       Tests Layer 2 connectivity
  Can reach remote hosts      Cannot cross routers

## Typical Workflow

1.  Find your subnet with `ip route`.
2.  Discover live hosts using `nmap -sn`.
3.  Test a specific device using `arping`.
4.  Scan open ports with `nmap`.

## Troubleshooting

### Timeout

The device is offline, not on your LAN, or using a different subnet.

### "Unable to automatically find interface"

Specify the interface manually:

``` bash
sudo arping -I wlan0 192.168.1.1
```

### Trying Google

``` bash
sudo arping google.com
```

This will fail because ARP works only on the local network. Use
`ping google.com` for Internet hosts.

## Best Practices

-   Use only on your own or authorized networks.
-   Use `nmap` or `arp-scan` to discover devices first.
-   Use `arping` to verify a specific local IP.

## Related Commands

``` bash
ip addr
ip route
ip neigh
ping
arp
arp-scan
nmap
```

## Legal Notice

Only use `arping` on networks you own or have permission to test.
