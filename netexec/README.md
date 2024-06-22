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

## smb protocol

	--shares : prints the smb shares
		if we arent getting anything try user filler usernames and passwords: netexec smb nest.htb -u 'aasdasd' -p 'adsasd' --shares
	--continues-on-sucess: don't stop when found a valid login, continue to test the others

## Usage Examples

Print protocol available modules

	netexec smb -L

Connect to smb server using a file for username and passwords

	netexec smb <target_ip> -u usernames.txt -p passwords.txt
	netexec smb nest.htb -u users.txt -p welcome2019 --continue-on-success

## More Information

https://www.netexec.wiki/