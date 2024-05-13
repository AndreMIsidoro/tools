# netexec

## Overview

NetExec (a.k.a nxc) is a network service exploitation tool that helps automate assessing the security of large networks.

Available protocols:

	smb
	ssh
	ldap
	ftp
	wmi
	winrm
	rdp
	vnc
	mssql

## Command

netexec

	<protocol> --help : shows protocol information
	<protocol> -L : shows protocols modules

## Usage Examples

Print protocol available modules

	netexec smb -L

Connect to smb server using a file for username and passwords

	netexec smb <target_ip> -u usernames.txt -p passwords.txt


## More Information

https://www.netexec.wiki/