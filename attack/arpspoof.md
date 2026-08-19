# arpspoof User Guide

## Overview

`arpspoof` is a network security testing tool from the **dsniff** suite.
It is used to simulate **ARP spoofing (ARP poisoning)** attacks on a
**local area network (LAN)** during authorized security assessments.

## Installation

``` bash
sudo apt update
sudo apt install dsniff
```

## Verify Installation

``` bash
arpspoof -h
```

## What is ARP?

ARP (Address Resolution Protocol) maps an IPv4 address to a MAC address
on a local network.

Example:

  IP Address      MAC Address
  --------------- -------------------
  192.168.1.1     AA:AA:AA:AA:AA:AA
  192.168.1.100   BB:BB:BB:BB:BB:BB

## What is ARP Spoofing?

ARP spoofing is the act of sending forged ARP replies so another device
associates an IP address with the wrong MAC address.

Conceptually:

``` text
Before

Victim  <------>  Router

After

Victim  --->  Attacker  --->  Router
```

This places the attacker between two devices on the LAN (a
Man-in-the-Middle position).

## Basic Syntax

``` bash
sudo arpspoof -i <interface> -t <victim-ip> <gateway-ip>
```

## Common Options

  Option   Description
  -------- -------------------------------
  -i       Network interface
  -t       Target IP address
  -r       Spoof both victim and gateway
  -h       Help

## Typical Security Testing Workflow

1.  Discover hosts on the LAN.
2.  Identify the gateway.
3.  Verify that the environment is authorized for testing.
4.  Use arpspoof to evaluate whether ARP spoofing protections exist.
5.  Restore the network after testing.

## Related Commands

``` bash
ip route
ip neigh
arping
arp-scan
nmap -sn
```

## Limitations

-   Works only on the local LAN.
-   Does not work across the Internet.
-   Modern defenses such as Dynamic ARP Inspection, static ARP entries,
    and encrypted protocols reduce the impact.

## arpspoof vs arping

  -----------------------------------------------------------------------
  arping                            arpspoof
  --------------------------------- -------------------------------------
  Tests whether a local IP responds Sends forged ARP replies during
  to ARP                            authorized testing

  Diagnostic tool                   Security assessment tool

  Checks one host                   Evaluates ARP spoofing resilience
  -----------------------------------------------------------------------

## Best Practices

-   Use only on networks you own or are authorized to test.
-   Prefer encrypted protocols (HTTPS, SSH, VPN).
-   Document findings and restore the network after testing.

## Legal Notice

Use `arpspoof` only for education, laboratory exercises, or authorized
penetration tests. Unauthorized use against networks or devices may be
illegal.
