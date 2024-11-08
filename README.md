# List Of Utilities for Escalation

## Blockchain

	foundry: toolkit for |Ethereum application development.

## Cheatsheets

	https://github.com/puzzithinker/cybersecurity_cheatsheets

## Credentials/Passwords Hunting

	windows
		mimikatz - extracts plaintext passwords, hash, PIN code and kerberos tickets from memory.
		Snaffler - Finds credentials in a windows AD environment

	pcap and network interfaces
		pcredz - hunts for credentials in pcap files
		net-creds - hunts for credentials in pcap files and network interfaces

	trufflehog - hunts for credentials in it, Jira, Slack, Confluence, Microsoft Teams, Sharepoint files/dirs

## Cryptography

	RSACTFTools

## Firmware

	binwalk - Binwalk is a fast, easy to use tool for analyzing, reverse engineering, and extracting firmware images.

## Fuzzing

	ffuf
	gobuster

## Hardware

	saleae - Hardware interface logic analyser

## Information Gathering

	nmap
	searchsploit : Used to find exploits
	wappalyzer : Used to find the technolagies used to build a webserver

## Ldap

	ldapDomainDump - Gathers informaition from a ldap environment
	bloodhound - BloodHound uses graph theory to reveal the hidden and often unintended relationships within an Active Directory or Azure environment
	bloodyAD - Interacts with the LDAP domain controoler in order to perform AD privesc
	impacket-dacledit.py - Python script to read and manage the Discretionary Access Control List of an object

## Ldap - Kerberos

	kerbrute - A tool to quickly bruteforce and enumerate valid Active Directory accounts through Kerberos Pre-Authentication

## Packets Analyser/Inspector

	snort

## Pwn Challenges

	pwntools	-	A python package with a command line interface with a lot of useful tools for ctf challenges

## Remote Desktop Protocol

	xfreerdp

## Subdomain/Vhost Scans

	gobuster dns
	knockpy
	fuff
	dnsrecon


## Web Proxies

	ZAP : open source tool to primary use of web proxies is to capture and replay HTTP requests
	Burp Suite : paid tool (with a free version) to primary use of web proxies is to capture and replay HTTP requests
	proxychains : routes all traffic coming from any command-line tool to any proxy we specify

## Execute Exploits

	metasploit

## Payload Generator

	msfvenom
	msfpayload

## Debugging and Reverse Engineering

	ghidra : ELF files
	immunity debugger : .exe files
	uncompyle6 : Python cross-version byte-code decompiler
	dnspy : .net decompiler https://github.com/dnSpy/dnSpy
	dotpeek: .net decompiler

	https://github.com/xiosec/Reverse-engineering

## Password and Hash Cracking

	JohnTheRipper: is a fast password cracker for offline
	hydra: passowrd cracker for online login
	hashcat: hash cracker

## Vulnerabilities Exploiter

	Responder: It's IPv6/IPv4 LLMNR/NBT-NS/mDNS Poisoner and NTLMv1/2 Relay.
	Evil-WinRM: This shell is the ultimate WinRM shell for hacking/pentesting.
	ssrfmap : Exploits the ssrf vulnerability

## Port Forwarding

	Chisel

## Utilities

	exiftool: Read and write meta information in files
	jq: Command line json processor
	zbarimg: scans image for bar and qr codes and prints any decoded data to stdout

## Windows

	Impacket: Network and sql protocols
	RunasCs: is an utility to run specific processes with different permissions than the user's current logon provides using explicit credentials.