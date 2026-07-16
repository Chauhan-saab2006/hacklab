# OSRFramework: Username Intelligence with `usufy`

OSRFramework is an open-source OSINT toolkit. Its `usufy` utility checks whether
a username may be in use across a range of online services. It is useful for
username research; it is **not** a subdomain-finding tool.

Use it only for lawful research, authorised security testing, or investigating
accounts you own.

## Install

On Debian or Ubuntu:

```bash
sudo apt update
sudo apt install osrframework
```

Confirm that the utility is available:

```bash
usufy --help
```

## Search for a Username

Replace `exampleuser` with the username you want to check:

```bash
usufy -n exampleuser
```

Review the results manually: an apparent match does not prove that every account
belongs to the same person.

## Example

```bash
usufy -n ocsaly
```

For the available filters, output options, and service selection, consult the
built-in help:

```bash
usufy --help
```
searchfy
```bash
searchfy -q "exampleuser"
```


And all the data will be save in csv file