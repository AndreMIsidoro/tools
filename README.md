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

## Debugging and Reverse Engineering

	ghidra : ELF files
	immunity debugger : .exe files
	uncompyle6 : Python cross-version byte-code decompiler
	dnspy : .net decompiler https://github.com/dnSpy/dnSpy
	dotpeek: .net decompiler
	ILSpy: .net decompiler (best one)

	https://github.com/xiosec/Reverse-engineering

## Exploits

	metasploit
	Evil-WinRM: This shell is the ultimate WinRM shell for hacking/pentesting.
	ssrfmap : Exploits the ssrf vulnerability
	xssstrike : Identifies xss vulnerabilities

## Firmware

	binwalk - Binwalk is a fast, easy to use tool for analyzing, reverse engineering, and extracting firmware images.

## Fuzzing

	ffuf
	gobuster

## Hardware

	saleae - Hardware interface logic analyser

## Host Discovery

	nmap
	fping

## Information Gathering

	searchsploit : Used to find exploits
	wappalyzer : Used to find the technolagies used to build a webserver

## Ldap

	enum4linux-ng - Basic enum of ldap services (RPC,SMB)
	ldapDomainDump - Gathers informaition from a ldap environment
	bloodhound - BloodHound uses graph theory to reveal the hidden and often unintended relationships within an Active Directory or Azure environment
	bloodyAD - Interacts with the LDAP domain controoler in order to perform AD privesc
	impacket-dacledit.py - Python script to read and manage the Discretionary Access Control List of an object
	impacket-secretdump - Python scrip extract sensitive information from a compromised system, such as password hashes, Kerberos tickets, and other credentials stored in Windows' LSASS (Local Security Authority Subsystem Service)
	powersploit - Collection of powershell modules

## Ldap - Kerberos

	kerbrute - A tool to quickly bruteforce and enumerate valid Active Directory accounts through Kerberos Pre-Authentication

## Packets Analyser/Inspector

	snort
	
## Password and Hash Cracking

	JohnTheRipper: is a fast password cracker for offline
	hydra: passowrd cracker for online login
	hashcat: hash cracker

## Password Spray

	kerbrute - Linux/Windows
	DomainPasswordSpay - Windows


## Payload Generator

	msfvenom
	msfpayload

## Poisoners

	responder: It's IPv6/IPv4 LLMNR/NBT-NS/mDNS Poisoner and NTLMv1/2 Relay.
	inveigh
	
## Port Forwarding and Tunneling

	Chisel
	ligolo-ng: An advanced, yet simple, tunneling tool

## Pwn Challenges

	pwntools	-	A python package with a command line interface with a lot of useful tools for ctf challenges

## Remote Desktop Protocol

	xfreerdp

## Subdomain/Vhost Scans

	gobuster dns
	knockpy
	fuff
	dnsrecon

## SMTP - Mail

	swaks - Swiss Army Knife SMTP, the all-purpose SMTP transaction tester


## Web Proxies

	ZAP : open source tool to primary use of web proxies is to capture and replay HTTP requests
	Burp Suite : paid tool (with a free version) to primary use of web proxies is to capture and replay HTTP requests
	proxychains : routes all traffic coming from any command-line tool to any proxy we specify

## Windows

	Impacket: Network and sql protocols
	RunasCs: is an utility to run specific processes with different permissions than the user's current logon provides using explicit credentials.

## Utilities

	exiftool: Read and write meta information in files
	jq: Command line json processor
	xmlstarlet: Command line xml processor. Similar to jq
	zbarimg: scans image for bar and qr codes and prints any decoded data to stdout