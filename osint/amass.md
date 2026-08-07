# Amass User Guide

## Overview

Amass is an OSINT and DNS enumeration tool for attack surface mapping.

## Installation

``` bash
sudo apt update
sudo apt install amass
```

## Verify

``` bash
amass -version
```

## Modes

-   `enum` - Subdomain enumeration
-   `intel` - Intelligence gathering
-   `viz` - Visualization
-   `track` - Compare scans
-   `db` - Query database

## Common Commands

Passive:

``` bash
amass enum -passive -d example.com
```

Active:

``` bash
amass enum -active -d example.com
```

Save output:

``` bash
amass enum -passive -d example.com -o subdomains.txt
```

Bruteforce:

``` bash
amass enum -brute -d example.com
```

Custom wordlist:

``` bash
amass enum -brute -w wordlist.txt -d example.com
```

Show IPs:

``` bash
amass enum -passive -ip -d example.com
```

Store project:

``` bash
amass enum -dir amass_output -d example.com
```

Database:

``` bash
amass db -dir amass_output -names
amass db -dir amass_output -assets
```

Intel:

``` bash
amass intel -d example.com
amass intel -asn 15169
```

Visualization:

``` bash
amass viz -dir amass_output
```

## Options

  Option     Meaning
  ---------- ---------------------
  -d         Target domain
  -passive   Passive enumeration
  -active    Active enumeration
  -brute     Bruteforce
  -o         Output file
  -dir       Project directory
  -w         Wordlist
  -ip        Resolve IPs

## Typical Workflow

1.  Passive enumeration
2.  Active enumeration
3.  Review results
4.  Probe live hosts with httpx
5.  Scan with Nmap
6.  Assess with Nuclei

## Best Practices

-   Use passive mode first.
-   Use active mode only with authorization.
-   Save results with `-dir` for later analysis.
-   Combine with other recon tools.

## Legal Notice

Only scan domains you own or have explicit permission to test.
