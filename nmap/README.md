# Nmap

## Overview

Nmap ("Network Mapper") is a free and open source utility for network discovery and security auditing
## Command Options

https://nmap.org/book/man-briefoptions.html

**Ports Scan**

	-p: Selects which port to scan
	--min-rate : This is used to specify the minimum number of packets that Nmap should
	send per second; it speeds up the scan as the number goes higher

**Script Scan**

	-A: Enable OS detection, version detection, script scanning, and traceroute
	-sC: equivalent to --script=default; runs default scripts
	-sV: Probe open ports to determine service/version info
    -sS: Stealth scan. It's the default scan with root privileges
	-oA <basename>: Output in the three major formats at once
	-Pn : Treat all hosts as online -- skip host discovery (good when dealing with firewalls)
	-sU : UDP scan


## Use nmap with a proxy (like Burp or ZAP)

Just add the --proxies flag to specify the proxy to be used:

	nmap --proxies http://127.0.0.1:8080 SERVER_IP -pPORT -Pn -sC
