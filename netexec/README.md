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

## SMB

	--shares : prints the smb shares
		if we arent getting anything try user filler usernames and passwords: netexec smb nest.htb -u 'aasdasd' -p 'adsasd' --shares
	--continues-on-sucess: don't stop when found a valid login, continue to test the others

### Usage Examples

Print protocol available modules

	netexec smb -L

Connect to smb server using a file for username and passwords

	netexec smb <target_ip> -u usernames.txt -p passwords.txt
	netexec smb nest.htb -u users.txt -p welcome2019 --continue-on-success


For smb using a TGT i'm having more success with the too:

```
impacket-smbclient
```


Download available shares:

```shell
netexec smb nest.htb -u users.txt -p welcome2019 -M spider_plus -o DOWNLOAD_FLAG=True
```

### Modules

	-M spider_plus - creates a json file with the file tree of the shares


## LDAP

Test if account exist without kereberos:

	nxc ldap 192.168.1.0/24 -u users.txt -p '' -k

Using TGT (it may require to add dc.rustykey.htb to /etc/hosts and use it):

```shell
export KRB5CCNAME=~/workspace/tmp/rustkey/rr.parker.ccache

faketime "$(ntpdate -q rustykey.htb | awk '{print $1" "$2}')" netexec ldap rustykey.htb -k -u 'rr.parker' -p '8#t5HE8L!W3A'
```

Test credentials:

	nxc ldap 192.168.1.0/24 -u user -H A29F7623FD11550DEF0192DE9246F46B

	nxc ldap 192.168.1.0/24 -u user -p password

Enumerate users:

	nxc ldap $ip -u $user -p $password --users
	nxc ldap $ip -u $user -p $password --active-users

https://www.netexec.wiki/ldap-protocol/authentication



## FTP

Test users

netexec ftp <server_ip> -u <userfile> -p <password_file> --no-bruteforce --continue-on_success

https://www.netexec.wiki/ftp-protocol/password-spraying

## More Information

https://www.netexec.wiki/